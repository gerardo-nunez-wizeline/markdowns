# LEHIGH-125: Analyze Bento data from WLVT migration

### Description

"WLVT uses PBS's Bento CMS to publish their news content. This ticket is to review the data provided by PBS so we can put together an LOE to migrate WLVT news stories to Grove."

**Jira Ticket:** [https://perfectsense.atlassian.net/browse/LEHIGH-125](https://perfectsense.atlassian.net/browse/LEHIGH-125)

### Data Models

<aside>
💡 The following JSON represent every unique data model in Bento WLVT Legacy data (aka. wlvt.json JAN 2023
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
                                    "placeholder": "Copyright \\u00a9 {% now 'Y' %} Public Broadcasting Service (PBS), all rights reserved. PBS is a 501(c)(3) not-for-profit organization.",
                                    "linkTo": {
                                        "externalHref": "",
                                        "filerUrl": "",
                                        "target": null,
                                        "pageId": null,
                                        "enabled": false
                                    },
                                    "id": "77dbefd9-329f-4a5c-94d8-d8c28e067d99",
                                    "replacements": [
                                        {
                                            "replace": "_currentYear_",
                                            "find": "{% now 'Y' %}"
                                        }
                                    ],
                                    "value": ""
                                },
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
                                },
                                {
                                    "placeholder": "Terms of Use",
                                    "id": "2d001afb-a88c-44b6-a824-32e8930d8d39",
                                    "linkTo": {
                                        "externalHref": "https://www.pbs.org/about/terms-use/",
                                        "filerUrl": "",
                                        "target": null,
                                        "pageId": null,
                                        "enabled": true
                                    },
                                    "value": "Terms of Use"
                                },
                                {
                                    "placeholder": "Marketing Preferences",
                                    "id": "6c339ab5-d90f-44ed-9255-4fb75011e885",
                                    "linkTo": {
                                        "externalHref": "https://www.pbs.org/about/pbs-privacy-policy/#Use_Cookies_Web_Beacons",
                                        "filerUrl": "",
                                        "target": null,
                                        "pageId": null,
                                        "enabled": true
                                    },
                                    "value": "Marketing Preferences"
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
                                            },
                                            {
                                                "value": "Join the PBS39 Leadership Society",
                                                "placeholder": "Link Item",
                                                "id": "83c0b386-aeee-4238-8351-9a0b9ba27f73",
                                                "linkTo": {
                                                    "externalHref": "",
                                                    "pageId": 1346,
                                                    "target": null,
                                                    "fileId": "",
                                                    "enabled": true
                                                },
                                                "hasLink": true
                                            },
                                            {
                                                "value": "PBS39 Cub Club",
                                                "placeholder": "Link Item",
                                                "id": "20ee75d9-9823-4478-9f7d-42b4164ca98b",
                                                "linkTo": {
                                                    "externalHref": "",
                                                    "pageId": 5040,
                                                    "target": null,
                                                    "fileId": "",
                                                    "enabled": true
                                                },
                                                "hasLink": true
                                            },
                                            {
                                                "value": "Local Programming Sponsorship",
                                                "placeholder": "Link Item",
                                                "id": "f222c33f-fa0a-4711-bc25-da9f1ebe1949",
                                                "linkTo": {
                                                    "externalHref": "",
                                                    "pageId": 15942,
                                                    "target": null,
                                                    "fileId": "",
                                                    "enabled": true
                                                },
                                                "hasLink": false
                                            },
                                            {
                                                "value": "Shop PBS",
                                                "placeholder": "Link Item",
                                                "id": "d36a33a4-5a2d-4bbd-a59e-e643166c631e",
                                                "linkTo": {
                                                    "externalHref": "https://shop.pbs.org/",
                                                    "pageId": null,
                                                    "target": "_blank",
                                                    "fileId": null,
                                                    "enabled": true
                                                },
                                                "hasLink": true
                                            },
                                            {
                                                "value": "Volunteer",
                                                "placeholder": "Link Item",
                                                "id": "dd07e004-acf5-439b-a6bf-e339b1622522",
                                                "linkTo": {
                                                    "externalHref": "",
                                                    "pageId": 17294,
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
        }
        "section_type": "footer",
        "creation_date": "2017-01-08T03:52:51.395Z",
        "modification_date": "2023-01-04T14:46:15.456Z"
    }
}
    ```
    

**Category Page**

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

```json
{
    "model": "bento_blog.entry",
    "pk": 286,
    "fields": {
        "content": "Capt. Robert Sponeybarger is a former POW who served during the Vietnam War in 1972-73. He shared photos with PBS39, which can be viewed below.",
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
