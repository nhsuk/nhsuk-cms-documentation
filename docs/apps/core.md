# Intro

The `core/` directory contains django apps which contain site-wide features.

## core/api

Provides methods for constructing an API response for the content api.

## core/cache_flush

Integration with the [cache flush api](https://github.com/nhsuk/cache-flush/).

## core/notify

Site setting providing ability to add pages to notify list. If a page is on the list and has been updated, api portal
subscribers will be informed.

## core/schema_org

Base page models providing [schema.org](https://schema.org) style fields which should be the base of all of our page types.

## core/user_feedback_form

Integration with the [user feedback form](https://github.com/nhsuk/user-feedback-form).

## core/aspect_management

Blocks and mixins providing functionality for tagging content sections with "aspect" data. Also known as "content modularisation".

## core/reports

Content usage reporting. Creates an index of content objects such as images, brightcove videos and tools, and which pages they appear on. The report can be viewed in the Wagtail admin interface.

## core/tools

Integration with the 3rd party interactive tools such as the BMI calculator, heart age calculator etc.

## core/videos

Integration with the [Brightcove](https://docs.brightcove.com/index.html) video hosting platform.

## core/workflow

Tools for sharing and approving content
