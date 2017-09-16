---
title: "Cómo: recuperar una WebResponse específica de protocolo que coincida con una WebRequest"
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
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
caps.latest.revision: 8
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7a6d3fbb7fe336487553a70f40478a022e6b5552
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# Cómo: recuperar una WebResponse específica de protocolo que coincida con una WebRequest
En este ejemplo se muestra cómo recuperar una WebResponse específica de protocolo que coincide con una WebRequest.  
  
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
  
-   Referencias al espacio de nombres **System.Net**.  
  
## Vea también  
 [Solicitud de datos](../../../docs/framework/network-programming/requesting-data.md)

