# granula

datasets modeling aproach with examples


# DataModels SQL naming mask:

    ## DataMart: model open for customers usage
        {granularity_type}_{filtering}_{dimension}_{usecase_details} //  filtering and usecase coule be skipped


        ### Names Examples:
            cubes:
                — cube_meta_ads_daily
                — cube_google_ads_daily
                — cube_ads_daily // if we going to union all sources/channels
                — cube_google_ads_montly_commulative // example with usecase details

            Entities:
                - entity_meta_campaigns
                — entity_google_ad_sets
                - entity_product_categories

            Events:
                - events_ga4
                - events_meta_adset_enablement_status_change_updates
                — events_crm_order_cancelations
                — events_airbyte_exttaction_log_status

        
 
    ## Intermediate DataModel: 
        {intermediate}_{granularity_type}_{filtering}_{dimension}_{usecase}

        ### Names Examples:
            - intermediate_cube_meta_ads_daily_with_campaign_name_fixes
            - intermediate_entity_creatives_with_accomulative_stats_materialized

    ## Source DataModel: 
        {source}_{granularity_type}_{filtering}_{dimension}_{usecase} // filtering and are not mundatory
   
         ### Names Examples:
            - source_cube_meta_ads_daily_with_campaign_name_fixes
            - intermediate_entity_creatives_with_accomulative_stats_materialized           



