An error occurred while communicating with data source 'steam_reviews'

```sql
Error Code: 73F9639A
[SQLSTATE:57014] canceled
SELECT "t2"."mn:Calculation_33565923760545797:ok" AS "mn:Calculation_33565923760545797:ok",
  "t2"."qr:Calculation_33565923760545797:ok" AS "qr:Calculation_33565923760545797:ok",
  SUM("steam_charts.csv"."averagePlayers") AS "sum:averagePlayers:ok",
  "t2"."yr:Calculation_33565923760545797:ok" AS "yr:Calculation_33565923760545797:ok"
FROM "db1001"."TableauTemp"."steam_charts#csv" "steam_charts.csv"
  INNER JOIN (
  SELECT "t1"."id" AS "id",
    "t1"."mn:Calculation_33565923760545797:ok" AS "mn:Calculation_33565923760545797:ok",
    "t1"."qr:Calculation_33565923760545797:ok" AS "qr:Calculation_33565923760545797:ok",
    "t1"."yr:Calculation_33565923760545797:ok" AS "yr:Calculation_33565923760545797:ok"
  FROM (
    SELECT "t0"."app_id" AS "id",
      CAST(TRUNC(EXTRACT(MONTH FROM TABLEAU.NORMALIZE_DATETIME("t0"."$temp0_cse"))) AS BIGINT OR NULL) AS "mn:Calculation_33565923760545797:ok",
      CAST(TRUNC(EXTRACT(QUARTER FROM TABLEAU.NORMALIZE_DATETIME("t0"."$temp0_cse"))) AS BIGINT OR NULL) AS "qr:Calculation_33565923760545797:ok",
      CAST(TRUNC(EXTRACT(YEAR FROM TABLEAU.NORMALIZE_DATETIME("t0"."$temp0_cse"))) AS BIGINT OR NULL) AS "yr:Calculation_33565923760545797:ok"
    FROM (
      SELECT "steam_reviews.csv"."app_id" AS "app_id",
        ((DATE '1970-01-01') + "sentiment_analysis_results_english.csv"."timestamp_created" * INTERVAL '1 SECOND') AS "$temp0_cse"
      FROM "db1002"."TableauTemp"."steam_reviews#csv" "steam_reviews.csv"
        LEFT JOIN "db1002"."TableauTemp"."sentiment_analysis_results_english#csv" "sentiment_analysis_results_english.csv" ON ("steam_reviews.csv"."app_name" = "sentiment_analysis_results_english.csv"."app_name")
      WHERE ("steam_reviews.csv"."app_name" = 'Grand Theft Auto V')
    ) "t0"
  ) "t1"
  GROUP BY 1,
    2,
    3,
    4
) "t2" ON ("steam_charts.csv"."id" = "t2"."id")
GROUP BY 1,
  2,
  4
```
