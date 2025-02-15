---
title: AD FS Troubleshooting - AD FS endpoints
description: This document describes how to troubleshoot AD FS endpoints
author: billmath
ms.author: billmath
manager: amycolannino
ms.date: 10/14/2024
ms.topic: article
---

# AD FS Troubleshooting - AD FS metadata endpoints
Endpoints provide access to the federation server functionality of AD FS, such as publishing federation metadata. To verify that the AD FS server is responding to web requests, we can check the various endpoints.


## Federation metadata test
Passive federation refers to scenarios where your browser is re-directed to the AD FS sign-in page. By testing the metadata endpoint, we can determine if the AD FS server is responding to web requests in these passive scenarios. Use the following procedure to test the endpoint.

1. Using a web browser, navigate to your AD FS Federation metadata endpoint. For example: https://sts.contoso.com/FederationMetadata/2007-06/FederationMetadata.xml
2. The xml file should download locally to your machine.
3. Open it and verify that it contains information similar to the information below:
![Passive](media/ad-fs-tshoot-endpoints/meta2.png)

## WS-MEX test (Active test)
WS-MetaDataExchange is a web services protocol and is part of the WS-Federation roadmap. It uses a SOAP message to request metadata. By testing the endpoint we can determine if the AD FS server is responding to web requests for WS-MetaDataExchange. Use the following procedure to test the endpoint.
1. Using a web browser, navigate to your AD FS Federation metadata endpoint. For example: https://sts.contoso.com/adfs/services/trust/mex
2. The xml file should be displayed in the browser automatically. It should look like the image below:

:::image type="content" source="media/ad-fs-tshoot-endpoints/security-trust-file.png" alt-text="A screenshot of the AD FS Federation metadata endpoint XML file.":::

## Next steps

- [AD FS Troubleshooting](ad-fs-tshoot-overview.md)
