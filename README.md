# indicia_reporting

Contains SQL and R script for summarising and extracting data from the BRC Indicia data warehouse (via e.g. DBeaver)

Requirements for all reports:
AND cache_occurrences_functional.training = FALSE

AND cache_occurrences_functional.website_id in (-- list of websites providing to irecord for reporting --)

List of Websites produced with:
select string_agg(from_website_id::text, ', ' order by from_website_id) from index_websites_website_agreements where to_website_id=23 and provide_for_reporting=TRUE
