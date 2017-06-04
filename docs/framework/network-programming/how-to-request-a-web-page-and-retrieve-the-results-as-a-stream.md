---
title: "C&#243;mo: solicitar una p&#225;gina web y recuperar los resultados como una secuencia | Microsoft Docs"
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
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# C&#243;mo: solicitar una p&#225;gina web y recuperar los resultados como una secuencia
En este ejemplo se muestra cómo solicitar una página Web y recuperar los resultados en una secuencia.  
  
## Ejemplo  
  
```csharp  
WebClient myClient = new WebClient();  
Stream response = myClient.OpenRead("http://www.contoso.com/index.htm");  
// The stream data is used here.  
response.Close();  
```  
  
```vb  
Dim myClient As WebClient = New WebClient()  
Dim response As Stream = myClient.OpenRead("http://www.contoso.com/index.htm")  
' The stream data is used here.  
response.Close()  
```  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los espacios de nombres <xref:System.IO> y <xref:System.Net>.  
  
## Vea también  
 [Solicitud de datos](../../../docs/framework/network-programming/requesting-data.md)