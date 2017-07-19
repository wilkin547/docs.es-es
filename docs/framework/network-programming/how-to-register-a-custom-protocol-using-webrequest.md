---
title: "C&#243;mo: registrar un protocolo personalizado mediante WebRequest | Microsoft Docs"
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
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# C&#243;mo: registrar un protocolo personalizado mediante WebRequest
En este ejemplo se muestra cómo registrar un protocolo que el classthatconcreto se define en otra parte.  En este ejemplo, `CustomWebRequestCreator` es el objeto usuario\-implementado que implementa el método de **Crear** que devuelve el objeto de `CustomWebRequest` .  El ejemplo de código supone que ha escrito `CustomWebRequest` codificado que aplica el protocolo personalizado.  
  
## Ejemplo  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
 Referencias al espacio de nombres <xref:System.Net> .  
  
## Vea también  
 [Programar protocolos acoplables](../../../docs/framework/network-programming/programming-pluggable-protocols.md)