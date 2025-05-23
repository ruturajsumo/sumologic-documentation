---
id: field-management
title: Field Management APIs
sidebar_label: Fields
description: Use Field Management APIs to manage your account's field table schema.
---

import useBaseUrl from '@docusaurus/useBaseUrl';
import ApiIntro from '../reuse/api-intro.md';
import ApiRoles from '../reuse/api-roles.md';

<img src={useBaseUrl('img/icons/operations/rules.png')} alt="Thumbnail icon" width="50"/>

The Field Management API allows you to configure fields from HTTP endpoints. Fields allow you to reference log data based on meaningful associations. They act as metadata tags that are assigned to your logs so you can search with them. Each field contains a key-value pair, where the field name is the key. For more information, see [Fields](/docs/manage/fields).

## Documentation

<ApiIntro/>

| Deployment | Documentation URL                                         |
|:------------|:-----------------------------------------------------------|
| AU         | https://api.au.sumologic.com/docs/#tag/fieldManagementV1  |
| CA         | https://api.ca.sumologic.com/docs/#tag/fieldManagementV1  |
| DE         | https://api.de.sumologic.com/docs/#tag/fieldManagementV1  |
| EU         | https://api.eu.sumologic.com/docs/#tag/fieldManagementV1  |
| FED        | https://api.fed.sumologic.com/docs/#tag/fieldManagementV1 |
| JP         | https://api.jp.sumologic.com/docs/#tag/fieldManagementV1  |
| KR         | https://api.kr.sumologic.com/docs/#tag/fieldManagementV1  |
| US1        | https://api.sumologic.com/docs/#tag/fieldManagementV1     |
| US2        | https://api.us2.sumologic.com/docs/#tag/fieldManagementV1 |

## Required role capabilities

<ApiRoles/>

* Data Management
    * Manage Field Extraction Rules
    * Manage Fields
    * View Field Extraction Rules
    * View Fields
