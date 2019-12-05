# PIG_AWS
Apache Pig for processing n-gram data

Apache Pig script for processing n-gram data on Amazon Web Services (AWS). Enter cutom bucket folder in the script.

Datasets: Dataset with over 130 million customer reviews from Amazon Customer Reviews downloadable from https://registry.opendata.aws/amazon-reviews/. 

Goal
Output the top 15 product categories having the highest average star rating per review along with their corresponding averages, in tab-separated format, sorted in descending order. Only consider entries whose review bodies are 100 characters or longer, have 30 or more total votes, and were verified purchases. If multiple product categories have the same average, order them alphabetically on product category. Refer to the example and calculations below:

product_id                review_id                star_rating

Toys                        RDIJS7QYB6XNR        3

Toys                        BAHDID7JDNAK0        4

Toys                        YHFKALWPEOFK4        2

Books                        BZHDKTLJYBDNE        4

Books                        ZZUDNFLGNALDA        3

Books                (4 + 3 ) / 2 = 3.5

Toys                (3 + 4 + 2) / 3        = 3.0



Sample Commands: Load data in PIG

To load data for the small example use the following command:

grunt> reviews = LOAD 's3://amazon-reviews-pds/tsv/amazon_reviews_us_M*' AS (marketplace:chararray,customer_id:chararray,review_id:chararray,product_id:chararray,product_parent:chararray,product_title:chararray,product_category:chararray,star_rating:int,helpful_votes:int,total_votes:int,vine:chararray,verified_purchase:chararray,review_headline:chararray,review_body:chararray, review_date:chararray);

