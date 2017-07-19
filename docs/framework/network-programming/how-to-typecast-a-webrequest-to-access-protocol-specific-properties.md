---
title: "C&#243;mo: convertir una WebRequest a propiedades espec&#237;ficas del protocolo de acceso | Microsoft Docs"
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
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# C&#243;mo: convertir una WebRequest a propiedades espec&#237;ficas del protocolo de acceso
Este ejemplo muestra cómo convertir un WebRequest para poder propiedades específicas del protocolo de acceso.  
  
## Ejemplo  
  
```csharp  
HttpWebRequest httpreq =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## Vea también  
 [Programar protocolos acoplables](../../../docs/framework/network-programming/programming-pluggable-protocols.md)