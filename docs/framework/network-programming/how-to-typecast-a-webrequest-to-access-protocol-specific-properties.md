---
title: "Cómo: convertir una WebRequest a propiedades específicas del protocolo de acceso"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
caps.latest.revision: 6
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 83c1d85f9f69eac42a9fa5c747819a76b754499d
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# Cómo: convertir una WebRequest a propiedades específicas del protocolo de acceso
En este ejemplo se muestra cómo convertir una WebRequest de manera que pueda tener acceso a las propiedades específicas del protocolo.  
  
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
 [Programming Pluggable Protocols (Programar protocolos acoplables)](../../../docs/framework/network-programming/programming-pluggable-protocols.md)

