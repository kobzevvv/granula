# DataModels SQL naming mask:

    ## DataMart: model open for customers usage
        {}_{dimension}_{filtering}_{usecase_details}//  filtering and usecase coule be skipped


        ### Names Examples:
            Cubes:
                — meta_ads_daily
                - google_ads_daily
                — google_ads_daily_campaigns 
                - all_ads_monthly_region_roas
                — all_ads_daily // if we going to union all sources/channels

            Entities:
                - meta_ads_campaigns
                — google_ad_sets
                - google_ads_keywords
                - meta_ads_creatives
                - all_ads_channels
                - countries

            Events:
                - ga4_events
                - meta_ads_events_settings_changes
                - shopify_events_sales_order_complited
                — events_crm_order_cancelations
                — events_airbyte_exttaction_log_status


    ## subject_domains
        - ads platforms domains
            — google_ads_
            — meta_ads_
            — pinterest_

        - analytics tools
            — ga4_
            - amplitude_

        our own domain
            — all_ads_ // models that unite all ads platforms data together

        customer data models
            - by_vbb_
        
 
    ## Intermediate DataModel: 
        {intermediate}_{granularity_type}_{filtering}_{dimension}_{usecase}

        ### Names Examples:
            - intermediate_daily_meta_ads_with_campaign_name_fixes
            - intermediate_entity_creatives_with_accomulative_stats_materialized

    ## Source DataModel: 
        {source}_{granularity_type}_{filtering}_{dimension}_{usecase} // filtering and are not mundatory
   
         ### Names Examples:
            - source_daily_meta_ads_with_campaign_name_fixes
            - intermediate_entity_creatives_with_accomulative_stats_materialized  

    ## metric layer on cubes         
        we use group by cube(dimensions) and add postfix _cube

from: https://github.com/kobzevvv/granula
