# Sixt Scraper Documentation

## Features

Sixt Scraper provides functionalities tailored to meet the requirements of retrieving specific data from Sixt's extensive repository:

More information on how to use this scraper here: https://apify.com/travelspider/sixt-scraper

- **Locations Query**: Allows users to discover Sixt rental locations based on specified search criteria, providing detailed information about each available rental location.
- **Rentals Query**: Focuses on extracting rental information such as available vehicles, pricing details, and rental quotes, aiding users in making well-informed rental decisions.

## Getting Started

### Input Parameters

Interacting with the Sixt Scraper API Wrapper necessitates providing specific input parameters, varying according to the query type. These parameters include:

- **`queryType`**: Type of query (`"locations"` or `"rentals"`). (String)
- **`searchLocation`**: Location to search for Sixt rental branches. (String) *For locations query only.*
- **`pickupLocationId`**: ID of the pickup location. (String) *For rentals query only.*
- **`returnLocationId`**: ID of the return location. (String) *For rentals query only.*
- **`pickupDateTime`**: Date and time of vehicle pickup in ISO format (YYYY-MM-DDTHH:MM). (String) *For rentals query only.*
- **`returnDateTime`**: Date and time of vehicle return in ISO format (YYYY-MM-DDTHH:MM). (String) *For rentals query only.*
- **`proxy`**: Configuration for using a proxy, with `useApifyProxy` as a boolean indicating whether to use Apify's proxy. (Object)

### Outputs

#### Locations

The output for the "locations" query type is an array of rental locations with the following attributes:

- **location_id**: The ID of the rental location.
- **title**: The title or name of the rental location.
- **description**: Description of the rental location.
- **type**: Type of location (e.g., airport).
- **is_sixt_branch**: Indicates if the location is a Sixt branch.
- **position**: Geographic coordinates of the location (latitude and longitude).
- **formatted_address**: Formatted address of the location.
- **branch**: Details about the branch, including ID, description, type, opening hours, holidays, vehicle types, directions, and more.
- **distance_meters**: Distance in meters from the search location. 

### Example Input locations

```json
{
  "queryType": "locations",
  "searchLocation": "Miami",
  "proxy": {
    "useApifyProxy": true
  }
}
```

#### Example Input Rentals

```json
{
  "queryType": "rentals",
  "pickupLocationId": "BRANCH:4",
  "returnLocationId": "BRANCH:4",
  "pickupDateTime": "2024-06-07T12:30",
  "returnDateTime": "2024-06-25T12:30",
  "proxy": {
    "useApifyProxy": true
  }
```

#### Example output Locations
```json
[
  {
    "location_id": "BRANCH:4",
    "title": "Miami Int Airport",
    "description": "3900 NW 25th Street #414, Miami, 33142, US",
    "type": "TYPE_AIRPORT",
    "is_sixt_branch": true,
    "position": {
      "latitude": 25.79823875427246,
      "longitude": -80.25975799560547
    },
    "formatted_address": "3900 NW 25th Street #414, Miami, 33142, US",
    "branch": {
      "id": "4",
      "location_id": "BRANCH:4",
      "title": "Miami Int Airport",
      "description": "3900 NW 25th Street #414, Miami, 33142, US",
      "type": "BRANCH_TYPE_AIRPORT",
      "position": {
        "latitude": 25.79823875427246,
        "longitude": -80.25975799560547
      },
      "formatted_address": "3900 NW 25th Street #414, Miami, 33142, US",
      "locality": "Miami",
      "has_24h_pickup": true,
      "has_24h_return": true,
      "is_24h_branch": true,
      "opening_hours": {
        "monday": [
          {
            "start": {
              "value": "00:00:00"
            },
            "end": {
              "value": "00:00:00"
            }
          }
        ],
        "tuesday": [
          {
            "start": {
              "value": "00:00:00"
            },
            "end": {
              "value": "00:00:00"
            }
          }
        ],
        "wednesday": [
          {
            "start": {
              "value": "00:00:00"
            },
            "end": {
              "value": "00:00:00"
            }
          }
        ],
        "thursday": [
          {
            "start": {
              "value": "00:00:00"
            },
            "end": {
              "value": "00:00:00"
            }
          }
        ],
        "friday": [
          {
            "start": {
              "value": "00:00:00"
            },
            "end": {
              "value": "00:00:00"
            }
          }
        ],
        "saturday": [
          {
            "start": {
              "value": "00:00:00"
            },
            "end": {
              "value": "00:00:00"
            }
          }
        ],
        "sunday": [
          {
            "start": {
              "value": "00:00:00"
            },
            "end": {
              "value": "00:00:00"
            }
          }
        ],
        "holidays": [
          {
            "start": {
              "value": "00:00:00"
            },
            "end": {
              "value": "00:00:00"
            }
          }
        ],
        "summaries": [
          {
            "start_day": "DAY_MONDAY",
            "end_day": "DAY_SUNDAY",
            "opening_hours_segments": [
              {
                "start": {
                  "value": "00:00:00"
                },
                "end": {
                  "value": "00:00:00"
                }
              }
            ]
          },
          {
            "start_day": "DAY_HOLIDAY",
            "end_day": "DAY_HOLIDAY",
            "opening_hours_segments": [
              {
                "start": {
                  "value": "00:00:00"
                },
                "end": {
                  "value": "00:00:00"
                }
              }
            ]
          }
        ]
      },
      "holidays": [
        {
          "value": "2024-07-04"
        },
        {
          "value": "2024-11-28"
        },
        {
          "value": "2024-12-25"
        }
      ],
      "fastlane_type": "FAST_LANE_TYPE_NO_FASTLANE",
      "vehicle_types": [
        "BRANCH_VEHICLE_TYPE_CONVERTIBLES",
        "BRANCH_VEHICLE_TYPE_JEEPS",
        "BRANCH_VEHICLE_TYPE_UNSPECIFIED",
        "BRANCH_VEHICLE_TYPE_PASSENGER_CARS",
        "BRANCH_VEHICLE_TYPE_VANS",
        "BRANCH_VEHICLE_TYPE_LUXURY_CARS"
      ],
      "vehicle_types_condensed": [
        "BRANCH_VEHICLE_TYPE_CONDENSED_CARS"
      ],
      "directions": [
        {
          "type": "DIRECTION_TYPE_OUT_OF_HOURS_RETURN",
          "title": "",
          "text": "Please drop your vehicle in the SIXT Return Area on Level 3. A SIXT Agent will be available to complete the check in. Thank you for choosing SIXT!"
        },
        {
          "type": "DIRECTION_TYPE_SHUTTLE",
          "title": "",
          "text": "SIXT at Miami Airport is located in the MIA Rental Car Center (RCC). From the arrival terminal, take the elevator and go on the 3rd level following the signs for the MIA mover (train) that will bring you directly to the Rental Car Center. The walkway on the 3rd floor will connect you to the train. Once at the Rental Car Center proceed to the main hall where you won't miss our bright orange counters located straight in front of you."
        },
        {
          "type": "DIRECTION_TYPE_LOCATION_DIRECTION",
          "title": "Your way to SIXT",
          "text": "SIXT at Miami Airport is located in the MIA Rental Car Center (RCC). From the arrival terminal, take the elevator and go on the 3rd level following the Center. The walkway on the 3rd floor will connect you to the train. Once at the Rental Car Center proceed to the main hall where you won't miss our bright orange counters located directly in front of you. Welcome!"
        },
        {
          "type": "DIRECTION_TYPE_LOCATION_DIRECTION",
          "title": "From the city of Miami",
          "text": "Please follow directions towards Miami Airport and look for green signs leading you to \"Rental Car Center\". Please proceed to the car rental center and drive up the ramp to Level 4, Passenger Pick-Up. Head all the way towards the end of the premises (passing the offsite car rental agency shuttle buses) and park in the designated 1-hour parking spots on the right side. Go through the sliding doors and follow the airport signs to our SIXT counters."
        },
        {
          "type": "DIRECTION_TYPE_LOCATION_DIRECTION",
          "title": "Return Information",
          "text": "To return your SIXT vehicle, please follow directions towards Miami Airport and look for green signs leading you to \"Rental Car Return\". Once at the Rental Car Center, please take the ramp to the 3rd floor and follow signs to the SIXT car return area. A SIXT staff member will be there to process your return. Then take the MIA Mover from the 4th floor back to the airport terminals. Please allow at least 20 minutes from the time of return to get back to the airport."
        }
      ],
      "hints": [],
      "country_code": "US",
      "out_of_hours": {
        "pickup": {
          "policy": "OUT_OF_HOURS_POLICY_NOT_ALLOWED",
          "information": ""
        },
        "return": {
          "policy": "OUT_OF_HOURS_POLICY_ALLOWED",
          "information": "Please drop your vehicle in the SIXT Return Area on Level 3. A SIXT Agent will be available to complete the check in. Thank you for choosing SIXT!"
        }
      },
      "timezone_id": "America/New_York",
      "is_e_vehicle_available": false,
      "is_meet_greet_branch": false,
      "meet_greet_note": "",
      "is_flight_number_mandatory": false,
      "requires_residence_country": false,
      "country_del_col_type": "ManualDelCol",
      "country_name": "USA"
    },
    "distance_meters": 0
  }
]
```

#### Example output Rentals
```json
[
  {
    "offer_matrix_id": "e04811ca-3c68-4338-a686-e5aed322226d",
    "offer_id": "CCAR-4-4",
    "car_info": {
      "product_type": "RENT",
      "group_type": "SEDAN",
      "guaranteed_model": false,
      "title": "Compact (Nissan Versa)",
      "subtitle": "or similar | Sedan",
      "mileage_formatted": "",
      "mileage_units_formatted": "",
      "car_age_formatted": "",
      "popularity": "",
      "rating": 0,
      "bags_count": 2,
      "small_bags_count": 2,
      "large_bags_count": 0,
      "passengers_count": 5,
      "minimum_driver_age": 21,
      "acriss_codes": "[CCAR]",
      "example_make_model": [
        "Compact (Nissan Versa)"
      ],
      "vehicle_images": [
        {
          "small_url": "https://www.sixt.com/fileadmin2/files/global/user_upload/fleet/png/350x200/nissan-versa-4d-grey-2023.png",
          "medium_url": "https://www.sixt.com/fileadmin2/files/global/user_upload/fleet/png/630x360/nissan-versa-4d-grey-2023.png",
          "large_url": "https://www.sixt.com/fileadmin2/files/global/user_upload/fleet/png/1050x600/nissan-versa-4d-grey-2023.png",
          "detail_desktop_url": "",
          "detail_mobile_url": "",
          "mini_url": "",
          "offer_tile_url": ""
        }
      ],
      "vehicle_images_v2": [
        {
          "key": "angleview",
          "images": [
            {
              "small_url": "https://www.sixt.com/fileadmin2/files/global/user_upload/fleet/png/350x200/nissan-versa-4d-grey-2023.png",
              "medium_url": "https://www.sixt.com/fileadmin2/files/global/user_upload/fleet/png/630x360/nissan-versa-4d-grey-2023.png",
              "large_url": "https://www.sixt.com/fileadmin2/files/global/user_upload/fleet/png/1050x600/nissan-versa-4d-grey-2023.png",
              "detail_desktop_url": "",
              "detail_mobile_url": "",
              "mini_url": "",
              "offer_tile_url": ""
            }
          ]
        },
        {
          "key": "sideview",
          "images": [
            {
              "small_url": "https://www.sixt.com/fileadmin2/files/global/sideview/user_upload/fleet/png/350x200/nissan-versa-4d-grey-2023.png",
              "medium_url": "https://www.sixt.com/fileadmin2/files/global/sideview/user_upload/fleet/png/752x500/nissan-versa-4d-grey-2023.png",
              "large_url": "https://www.sixt.com/fileadmin2/files/global/sideview/user_upload/fleet/png/1050x600/nissan-versa-4d-grey-2023.png",
              "detail_desktop_url": "",
              "detail_mobile_url": "",
              "mini_url": "",
              "offer_tile_url": ""
            }
          ]
        }
      ],
      "transmission_type": "TRANSMISSION_TYPE_AUTOMATIC",
      "transmission_type_v2": "TRANSMISSION_TYPE_V2_AUTOMATIC",
      "driver_requirements": {
        "minimum_age": 21,
        "young_driver": 25,
        "license_min_years": 0,
        "license_category": ""
      },
      "navigation_included": false,
      "is_electric": false,
      "charging_cable": "",
      "is_luxury": false,
      "doors_count": 4
    },
    "rate_code": "US9PU000",
    "deposit": {
      "currency_code": "EUR",
      "value": 185
    },
    "deposit_in_local_currency": {
      "currency_code": "USD",
      "value": 200
    },
    "price_total": {
      "gross": {
        "currency_code": "EUR",
        "value": 665.03
      },
      "net": {
        "currency_code": "EUR",
        "value": 621.52
      },
      "tax": {
        "currency_code": "EUR",
        "value": 43.51
      },
      "display_amount": {
        "currency_code": "EUR",
        "value": 665.03
      },
      "price_unit": "PRICE_UNIT_RENTAL",
      "display_suffix": "total",
      "tracking_net": {
        "currency_code": "EUR",
        "value": 621.52
      }
    },
    "price_per_day": {
      "gross": {
        "currency_code": "EUR",
        "value": 26
      },
      "net": {
        "currency_code": "EUR",
        "value": 24.3
      },
      "tax": {
        "currency_code": "EUR",
        "value": 1.7
      },
      "display_amount": {
        "currency_code": "EUR",
        "value": 24.3
      },
      "price_unit": "PRICE_UNIT_PER_DAY",
      "display_suffix": "/ day",
      "tracking_net": {
        "currency_code": "EUR",
        "value": 24.3
      }
    },
    "promo_label": "",
    "mileage_included_formatted": "Unlimited miles",
    "pickup_datetime": {
      "value": "2024-06-07T12:30:00"
    },
    "return_datetime": {
      "value": "2024-06-25T12:30:00"
    },
    "calculated_rental_days": 18,
    "calculated_rental_hours": 0,
    "offer_availability_status": "OFFER_AVAILABILITY_STATUS_FREE_SALE",
    "mileage_plans": [
      {
        "plan_number": "1",
        "is_selected": true,
        "is_unlimited": true,
        "distance": {
          "distance": "0",
          "distance_unit": "DISTANCE_UNIT_MILES"
        },
        "total_amount": {
          "gross": {
            "currency_code": "EUR",
            "value": 665.03
          },
          "net": {
            "currency_code": "EUR",
            "value": 621.52
          },
          "tax": {
            "currency_code": "EUR",
            "value": 43.51
          },
          "display_amount": {
            "currency_code": "EUR",
            "value": 665.03
          },
          "price_unit": "PRICE_UNIT_RENTAL",
          "display_suffix": "total",
          "tracking_net": {
            "currency_code": "EUR",
            "value": 621.52
          }
        },
        "base_amount": {
          "gross": {
            "currency_code": "EUR",
            "value": 468
          },
          "net": {
            "currency_code": "EUR",
            "value": 437.39
          },
          "tax": {
            "currency_code": "EUR",
            "value": 30.61
          },
          "display_amount": {
            "currency_code": "EUR",
            "value": 437.39
          },
          "price_unit": "PRICE_UNIT_RENTAL_BASE",
          "display_suffix": "base price",
          "tracking_net": {
            "currency_code": "EUR",
            "value": 437.39
          }
        },
        "total_price_difference": {
          "currency_code": "EUR",
          "value": 0
        },
        "additional_info": {
          "name": "Long Distance",
          "description": "",
          "icon": {
            "id": "MileagePlanLarge",
            "url": "https://cdn.sixt.io/rent/mileage_long.png"
          },
          "line_item_info": [
            {
              "name": "Unlimited miles",
              "description": "",
              "display_category": "DISPLAY_CATEGORY_INCLUDED",
              "display_group": "DISPLAY_GROUP_NON_COLLAPSIBLE"
            }
          ],
          "description_long": "",
          "promo_label": ""
        },
        "total_price_difference_display_suffix": "/one-time",
        "total_price_difference_per_day": {
          "currency_code": "EUR",
          "value": 0
        },
        "total_price_difference_per_day_display_suffix": "/day",
        "additional_info_v2": {
          "title": "Unlimited miles",
          "subtitle": "All miles are included in the price"
        },
        "offer_list_price_difference_per_day": {
          "currency_code": "EUR",
          "value": 0
        },
        "offer_list_price_difference_per_day_display_suffix": "/day"
      }
    ],
    "presentation_attributes_v2": [
      {
        "id": "numberOfPassengers",
        "name": "numberOfPassengers",
        "value": "5"
      },
      {
        "id": "transmissionTypeV2",
        "name": "AUTOMATIC",
        "value": "Automatic"
      },
      {
        "id": "doors",
        "name": "doors",
        "value": "4"
      },
      {
        "id": "minDriverAge",
        "name": "minDriverAge",
        "value": "21"
      }
    ],
    "is_young_driver_fee_applied": false,
    "offer_highlighted_features": [
      "Unlimited miles"
    ]
  }
]
```
