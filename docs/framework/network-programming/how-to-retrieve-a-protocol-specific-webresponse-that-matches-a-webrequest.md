---
title: "C&#243;mo: recuperar una WebResponse espec&#237;fica de protocolo que coincida con una WebRequest | Microsoft Docs"
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
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# C&#243;mo: recuperar una WebResponse espec&#237;fica de protocolo que coincida con una WebRequest
Este ejemplo muestra cómo recuperar un WebResponse protocolo\- concreto que coincide con un WebRequest.  
  
## Ejemplo  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias al espacio de nombres **System.Net** .  
  
## Vea también  
 [Solicitud de datos](../../../docs/framework/network-programming/requesting-data.md)