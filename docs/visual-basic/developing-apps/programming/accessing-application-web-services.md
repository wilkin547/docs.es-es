---
title: "Acceso a los servicios Web de aplicaciones (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "aplicaciones [Visual Basic], servicios Web"
  - "My.WebServices (objeto)"
  - "servicios Web, My.WebServices (objeto)"
ms.assetid: 8ad5405b-e771-42b1-82d3-ce97af2cea9e
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Acceso a los servicios Web de aplicaciones (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El objeto `My.WebServices` proporciona una instancia de cada servicio Web al que hace referencia el proyecto actual.  Cada una de las instancias se crea a petición.  Puede tener acceso a estos servicios Web a través de las propiedades del objeto `My.WebServices`.  El nombre de la propiedad es igual que el nombre del servicio Web al que tiene acceso la propiedad.  Cualquier clase que herede de <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> es un servicio Web.  
  
## Tareas  
 La tabla siguiente muestra las posibles maneras de tener acceso a los servicios Web a los que hace referencia una aplicación.  
  
|||  
|-|-|  
|Para|Vea|  
|Llamar a un servicio Web|[My.WebServices \(Objeto\)](../../../visual-basic/language-reference/objects/my-webservices-object.md)|  
|Llamar de manera asincrónica a un servicio Web y controlar un evento cuando finaliza|[Cómo: Llamar a un servicio Web de forma asincrónica](../../../visual-basic/developing-apps/programming/how-to-call-a-web-service-asynchronously.md)|  
  
## Vea también  
 [My.WebServices \(Objeto\)](../../../visual-basic/language-reference/objects/my-webservices-object.md)