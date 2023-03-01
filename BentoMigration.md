# LEHIGH-45: Analyze Bento data from WLVT migration

### Description

"WLVT uses PBS's Bento CMS to publish their news content. This ticket is to review the data provided by PBS so we can put together an LOE to migrate WLVT news stories to Grove."

**Jira Ticket:** [https://perfectsense.atlassian.net/browse/LEHIGH-12](https://perfectsense.atlassian.net/browse/LEHIGH-125)

### Data Models

<aside>
💡 The following JSON represent every unique data model in Bento WLVT Legacy data (aka. wlvt.json JAN 2023).
</aside>

**Site**

```json
{
    "model": "sites.site",
    "fields": {
        "domain": "www.wlvt.org",
        "name": "PBS39 WLVT"
    }
}
```

**Site Role**

<aside>
💡 Analyzing the main changes in the JSON structure, many changes are related to how the IDs are handled, the clearest example is in '"bento_cms.siterole"' in which we can see that in the previous structure the fields were strings and now they are IDs.
<aside>
<br />
    
OLD

```json 
{
    "pk": 37443,
    "model": "bento_cms.siterole",
    "fields": {
        "site": [
            "www.wlvt.org"
        ],
        "user": [
            "chloen"
        ],
        "group": [
            "editors"
        ]
    }
}
```

NEW
```json
{
    "model": "bento_cms.siterole",
    "pk": 51128,
    "fields": {
        "site": 23,
        "group": 3,
        "user": 674
    }
}
```


- **Site Section**

OLD

```json
    {
       "pk": 45,
       "model": "bento_cms.sitesection",
       "fields": {
          "site": [
             "www.wlvt.org"
          ],
          "content": {
             "columns": {
                "9c7a3652-bec6-40eb-a710-23b8e4eecbb3": {
                   "components": [
                      "ba060610-f24d-11e7-8939-c794e528d222",
                      "16b13c80-0ca6-11ea-9cf5-11279dd89bbb",
                      "2da56560-0ca6-11ea-9cf5-11279dd89bbb",
                      "f22cd4a0-9fc8-11e8-aa3b-b35b3242189c"
                   ],
                   "id": "9c7a3652-bec6-40eb-a710-23b8e4eecbb3",
                   "size": 12
                }
             },
             "components": {
                "f22cd4a0-9fc8-11e8-aa3b-b35b3242189c": {
                   "id": "f22cd4a0-9fc8-11e8-aa3b-b35b3242189c",
                   "data": {},
                   "verboseName": "station header",
                   "name": "station-header",
                   "restriction": {
                      "allowedColumns": [
                         12
                      ],
                      "allowedSections": [
                         "header"
                      ],
                      "allowedSiteTypes": [
                         "station"
                      ]
                   },
                   "settings": {
                      "showSearch": true,
                      "cls": "navbar-nav",
                      "showLogo": true,
                      "isSticky": true,
                      "hasHighlight": true
                   }
                },
                "ba060610-f24d-11e7-8939-c794e528d222": {},
                "2da56560-0ca6-11ea-9cf5-11279dd89bbb": {},
                "16b13c80-0ca6-11ea-9cf5-11279dd89bbb": {}
             },
             "layouts": {
                "dc9a6435-f32d-41bf-91d1-2aa885d16088": {
                   "showBackgroundImage": false,
                   "columns": [
                      "9c7a3652-bec6-40eb-a710-23b8e4eecbb3"
                   ],
                   "backgroundColor": "#ff0000",
                   "name": "",
                   "id": "dc9a6435-f32d-41bf-91d1-2aa885d16088",
                   "showBackgroundColor": true
                }
             },
             "section": {
                "layouts": [
                   "dc9a6435-f32d-41bf-91d1-2aa885d16088"
                ]
             },
             "operation": {}
          },
          "section_type": "header",
          "creation_date": "2017-01-08T03:52:51.391Z",
          "modification_date": "2021-03-25T17:57:37.535Z"
       }
    }
```

NEW    
```json
    {
    "model": "bento_cms.sitesection",
    "pk": 46,
    "fields": {
        "site": 23,
        "content": {
                "columns": {
                    "8f580a41-fcbc-4ad5-a9a5-e4a00dfa1a72": {
                        "size": 12,
                        "id": "8f580a41-fcbc-4ad5-a9a5-e4a00dfa1a72",
                        "components": [],
                        "columnSizeOnDisplay": 3
                    }
                },
                "layouts": {
                    "21b0c421-8a09-4443-ad54-df7f0a3f5dab": {
                        "columns": [
                            "8f580a41-fcbc-4ad5-a9a5-e4a00dfa1a72"
                        ],
                        "showBackgroundImage": false,
                        "id": "21b0c421-8a09-4443-ad54-df7f0a3f5dab",
                        "showBackgroundColor": false,
                        "name": ""
                    }
                },
                "components": {
                    "47843c50-02ee-11e7-9785-939b055e98b5": {
                        "restriction": {
                            "allowedColumns": {},
                            "allowedSections": {},
                            "allowedSiteTypes": {}
                        },
                        "id": "47843c50-02ee-11e7-9785-939b055e98b5",
                        "data": {
                            "compact": {
                                "links": []
                            },
                            "logo": {
                                "label": "PBS39-2019-Blue.png",
                                "isDefault": false,
                                "linkTo": {
                                    "externalHref": "",
                                    "pageId": null,
                                    "target": null,
                                    "enabled": false
                                },
                                "id": 96264,
                                "url": "https://d1qbemlbhjecig.cloudfront.net/prod/filer_public/wlvt2-pbs/2019%20PBS39%20Blue/e5fd2adf69_PBS39-2019-Blue.png",
                                "icon": "https://d1qbemlbhjecig.cloudfront.net/prod/filer_public_thumbnails/filer_public/wlvt2-pbs/2019%20PBS39%20Blue/e5fd2adf69_PBS39-2019-Blue.png__32x32_q85_crop_subsampling-2_upscale.png"
                            },
                            "copyrightLinks": [
                                {
                                    "placeholder": "Privacy Policy",
                                    "id": "53bf8251-b5c3-4beb-84b1-eca670e44f4f",
                                    "linkTo": {
                                        "externalHref": "https://www.pbs.org/about/pbs-privacy-policy/",
                                        "filerUrl": "",
                                        "target": null,
                                        "pageId": null,
                                        "enabled": true
                                    },
                                    "value": "Privacy Policy"
                                }
                            ],
                            "expanded": {
                                "details": "Univest Public Media Center<br>839 Sesame Street<br>Bethlehem, PA 18015<br><br>Phone: 610-867-4677<br>Fax: 610-867-3544",
                                "links": [
                                    {
                                        "header": {
                                            "value": "DONATE &amp; SUPPORT PBS39",
                                            "placeholder": "Column Header",
                                            "id": "ad6fa6c5-e29d-44fd-98df-7a1e28f71917",
                                            "linkTo": {
                                                "externalHref": "",
                                                "pageId": 1069,
                                                "target": null,
                                                "fileId": null,
                                                "enabled": true
                                            },
                                            "hasLink": false
                                        },
                                        "list": [
                                            {
                                                "value": "Become a Member",
                                                "placeholder": "Link Item",
                                                "id": "44e8fa28-5331-4a77-93c1-3eaa786ed164",
                                                "linkTo": {
                                                    "externalHref": "",
                                                    "pageId": 1101,
                                                    "target": null,
                                                    "fileId": "",
                                                    "enabled": true
                                                },
                                                "hasLink": true
                                            }
                                        ]
                                    }
                                ],
                                "detailsPlaceholder": "Details",
                                "icons": [],
                                "logo": {
                                    "label": "PBS39-2019-Blue.png",
                                    "isDefault": false,
                                    "linkTo": {
                                        "externalHref": "",
                                        "pageId": null,
                                        "target": null,
                                        "enabled": false
                                    },
                                    "id": 96264,
                                    "url": "https://d1qbemlbhjecig.cloudfront.net/prod/filer_public/wlvt2-pbs/2019%20PBS39%20Blue/e5fd2adf69_PBS39-2019-Blue.png",
                                    "icon": "https://d1qbemlbhjecig.cloudfront.net/prod/filer_public_thumbnails/filer_public/wlvt2-pbs/2019%20PBS39%20Blue/e5fd2adf69_PBS39-2019-Blue.png__32x32_q85_crop_subsampling-2_upscale.png"
                                },
                                "socialText": "Connect with us"
                            }
                        },
                        "settings": {
                            "showDetails": true,
                            "type": "expanded",
                            "background": "light",
                            "showLogo": true,
                            "logoAltText": "PBS39/WLVT",
                            "showSocial": true,
                            "showCopyright": false,
                            "showHeader": [
                                true,
                                true,
                                true,
                                true
                            ]
                        },
                        "verboseName": "Flexible Footer",
                        "name": "flexible-footer",
                        "icon": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABoAAAAbCAYAAABiFp9rAAAAAXNSR0IArs4c6QAAAIxJREFUSA1jFMrftpXh/38vBloCRsZtTDS3BOQBoEeYaOkRZLNZkDnvJnkzIvMpZQvlbf0PM4NuPhq1CBbkJNOjQUdykME0jAYdLCRIpodf0KEUqrDwQC4MYWKk0NgK5+EXdKM+IiVNoKjFmuqwpRoUXWRw6BZHjJTmGWI9RzcfMTEAW5HEuopsdUA7AG2qFyebyRZmAAAAAElFTkSuQmCC"
                    }
                },
                "section": {
                    "layouts": [
                        "21b0c421-8a09-4443-ad54-df7f0a3f5dab"
                    ]
                },
                "operation": {}
        },
        "section_type": "footer",
        "creation_date": "2017-01-08T03:52:51.395Z",
        "modification_date": "2023-01-04T14:46:15.456Z"
    }
}
```
    

**Category Page**


OLD

```json
{
    "model": "bento_cms.categorypage",
    "fields": {
        "page": [
            "/blogs/carbon",
            "www.wlvt.org"
        ],
        "category": [
            "carbon",
            "www.wlvt.org"
        ]
    }
},
```

NEW

```json
{
    "model": "bento_cms.categorypage",
    "pk": 27,
    "fields": {
        "page": 2343,
        "category": 27
    }
},
```

**Blog Category**

OLD
```json
{
    "model": "bento_blog.category",
    "fields": {
        "disqus_shortname": "",
        "delete_date": null,
        "site": [
            "www.wlvt.org"
        ],
        "branding_image": null,
        "slug": "carbon",
        "title": "Carbon"
    }
},
```
OLD

```json
{
    "model": "bento_blog.category",
    "pk": 74,
    "fields": {
        "title": "The War Is Still With Us - Community Photos",
        "slug": "the-war",
        "site": 23,
        "branding_image": null,
        "disqus_shortname": "",
        "delete_date": null
    }
},
```

**Blog Entry**

OLD
```json
{
    "model": "bento_blog.entry",
    "fields": {
        "content": "...",
        "show_author": true,
        "publication_date": "2020-12-18T02:03:13.701Z",
        "slug": "boilo-tradition-lives-on-in-the-coal-region",
        "show_social_icons": true,
        "seo_title": "",
        "credit": "",
        "is_published": true,
        "start_publication": "2020-12-18T03:51:30.212Z",
        "authors": [
            [
                "Haley O'Brien",
                "haleyo"
            ]
        ],
        "disqus_enabled": true,
        "update_date": "2020-12-18T03:51:30.225Z",
        "category": [
            "carbon",
            "www.wlvt.org"
        ],
        "image_alt_text": "",
        "custom_publication_date": null,
        "show_post_date": true,
        "enable_poster_image": true,
        "title": "Boilo Tradition Lives on in the Coal Region",
        "meta_keywords": "",
        "modified_at": "2020-12-18T03:51:30.225Z",
        "poster_image": "https://d1qbemlbhjecig.cloudfront.net/prod/filer_public/wlvt2-pbs/ebda298f18_boilo.jpg",
        "short_description": "The high-octane beverage has been passed down through generations.",
        "delete_date": null,
        "caption": "",
        "end_publication": null
    }
},
```

NEW

```json
{
    "model": "bento_blog.entry",
    "pk": 286,
    "fields": {
        "content": "...",
        "title": "Col. Robert Sponeybarger: U.S. Air Force",
        "slug": "capt-robert-sponeybarger",
        "short_description": "Former POW served during the Vietnam War from 1972-73.",
        "start_publication": "2017-10-11T14:23:30.411Z",
        "end_publication": null,
        "publication_date": "2017-10-11T14:23:30.411Z",
        "custom_publication_date": null,
        "is_published": false,
        "modified_at": "2017-10-11T14:23:28.841Z",
        "update_date": "2017-10-11T14:23:28.841Z",
        "show_post_date": true,
        "category": 74,
        "show_author": true,
        "seo_title": "",
        "meta_keywords": "",
        "disqus_enabled": true,
        "poster_image": "https://d1qbemlbhjecig.cloudfront.net/prod/filer_public/wlvt2-pbs/The%20War%20is%20Still%20With%20Us/Capt.%20Robert%20Sponeybarger/df5995f669_002.jpg",
        "enable_poster_image": true,
        "caption": "",
        "image_alt_text": "",
        "credit": "",
        "show_social_icons": true,
        "delete_date": null,
        "authors": [
            323
        ]
    }
}
```

**Entry Authors**

OLD
```json
{
    "pk": 134746,
    "model": "bento_blog.entry_authors",
    "fields": {
        "entry": [
            "kids-for-the-community",
            "carbon",
            "www.wlvt.org"
        ],
        "author": [
            "Haley O'Brien",
            "haleyo"
        ]
    }
},
```
NEW
```json
{
    "model": "bento_blog.entry_authors",
    "pk": 1613,
    "fields": {
        "entry": 291,
        "author": 323
    }
}
```


**Entry Page**

OLD 
```json
{
    "model": "bento_cms.entrypage",
    "fields": {
        "entry": [
            "kids-for-the-community",
            "carbon",
            "www.wlvt.org"
        ],
        "page": [
            "/blogs/carbon/kids-for-the-community",
            "www.wlvt.org"
        ]
    }
},
```
NEW

```json
{
    "model": "bento_cms.entrypage",
    "pk": 20624,
    "fields": {
        "page": 52523,
        "entry": 20624
    }
},
```

**Page**

OLD

```json
{
    "model": "bento_cms.page",
    "fields": {
        "meta_description": "",
        "show_disqus": false,
        "has_footer": true,
        "has_indexing": true,
        "modification_date": "2019-03-02T17:00:57.584Z",
        "media_image": 68665,
        "has_header": true,
        "title": "Governor Wolf's Proposed Minimum Wage Increase Could Hurt Economy",
        "path": "/blogs/carbon/governor-wolfs-proposed-minimum-wage-increase-could-hurt-economy",
        "special_page_type": null,
        "meta_title": "",
        "page_type": "default",
        "site": [
            "www.wlvt.org"
        ],
        "delete_date": null,
        "meta_tags": "minimum wage,governor tom wolf,governor,pennsylvania,pennsylvania minimum wage,increase,economy,blue mountain resort,small business,harrisburg,carbon county",
        "rail_type": null
    }
},
```
NEW

```json
{
    "model": "bento_cms.page",
    "pk": 52524,
    "fields": {
        "title": "WLVR 91.3 Election Day Coverage",
        "path": "/blogs/northampton/wlvr-913-election-day-coverage",
        "site": 23,
        "has_header": true,
        "has_footer": true,
        "page_type": "post",
        "rail_type": null,
        "media_image": null,
        "meta_tags": "wlvr,radio,pbs39,election",
        "meta_description": "",
        "meta_title": "",
        "has_indexing": true,
        "show_disqus": false,
        "delete_date": null,
        "special_page_type": null,
        "modification_date": "2019-12-24T14:52:11.269Z"
    }
}
```

**Content Version**

OLD
```json
{
    "model": "bento_cms.contentversion",
    "fields": {
        "content": "...",
        "last_editor": [
            "dawaynec"
        ],
        "creation_date": "2017-09-18T13:52:52.941Z",
        "page": [
            "/thewar",
            "www.wlvt.org"
        ],
        "modification_date": "2019-02-06T09:13:07.810Z",
        "publication_end": "2017-10-03T19:04:15.715Z",
        "display_name": "Draft",
        "publication_start": "2017-09-18T13:53:05.460Z"
    }
},
```
NEW

```json
{
    "model": "bento_cms.contentversion",
    "pk": 74468,
    "fields": {
        "page": 12452,
        "display_name": "default",
        "content": "...",
        "creation_date": "2018-08-16T22:35:33.383Z",
        "modification_date": "2019-02-06T09:11:08.764Z",
        "publication_start": "2018-08-16T22:35:33.388Z",
        "publication_end": "2018-08-16T22:35:47.185Z",
        "last_editor": null
    }
},
```

**Redirect**

OLD
```json
{
    "model": "bento_cms.redirect",
    "fields": {
        "new_path": "/about/volunteer",
        "modification_date": "2020-10-13T11:16:02.675Z",
        "site": [
            "www.wlvt.org"
        ],
        "old_path": "/Volunteer",
        "creation_date": "2020-10-13T11:16:02.675Z",
        "redirect_type": 301
    }
},
```

NEW
```json
{
    "model": "bento_cms.redirect",
    "pk": 21815,
    "fields": {
        "redirect_type": 301,
        "site": 23,
        "old_path": "/143Day",
        "new_path": "/folder/143-day",
        "creation_date": "2020-10-13T11:16:02.675Z",
        "modification_date": "2020-10-13T11:16:02.675Z"
    }
},
```

