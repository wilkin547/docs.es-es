---
title: "C&#243;mo: Reemplazar una selecci&#243;n del Proxy Global | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# C&#243;mo: Reemplazar una selecci&#243;n del Proxy Global
Este ejemplo envía **WebRequest** a www.contoso.com que reemplaza la selección global de proxy con un servidor proxy denominado `alternateproxy` en el puerto 80.  
  
## Ejemplo  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias al espacio de nombres **System.Net** .  
  
## Vea también  
 [Usar protocolos de aplicaciones](../../../docs/framework/network-programming/using-application-protocols.md)   
 [Acceso a Internet a través de un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)