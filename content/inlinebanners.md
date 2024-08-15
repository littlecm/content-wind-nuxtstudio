---
title: Inline Banners
description: A page to display inline banners fetched from an API
---

#default
::div{.container.mx-auto.p-4}
# Inline Banners

| Account ID                             | &#xA;Desktop Image                                                             | &#xA;Mobile Image                                                            | &#xA;URL&#xA;                                                                                                |
| -------------------------------------- | ------------------------------------------------------------------------------ | ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| &#xA;&#xA;      {{ banner.accountid }} | &#xA;![Desktop Image](undefined){.w-32.h-auto :src="banner.desktopimage"}&#xA; | &#xA;![Mobile Image](undefined){.w-32.h-auto :src="banner.mobileimage"}&#xA; | &#xA;[{{ banner.url }}](){.text-blue-500.underline :href="banner.url"}&#xA;&#xA;        &#xA;      &#xA;     |
::
