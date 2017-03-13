---
title: "My.Response (Objeto) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "My.MyWebExtension.Response"
  - "My.Response"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Response (objeto)"
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# My.Response (Objeto)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Obtiene el objeto <xref:System.Web.HttpResponse> asociado a la página <xref:System.Web.UI.Page>.  Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.  
  
## Comentarios  
 El objeto `My.Response` contiene el objeto <xref:System.Web.HttpResponse> actual asociado a la página.  
  
 El objeto `My.Response` solo está disponible para las aplicaciones [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)].  
  
## Ejemplo  
 El ejemplo siguiente obtiene la colección de encabezados del objeto `My.Request` y utiliza el objeto `My.Response` para escribirlo en la página ASP.NET.  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## Vea también  
 <xref:System.Web.HttpResponse>   
 [My.Request \(Objeto\)](../../../visual-basic/language-reference/objects/my-request-object.md)