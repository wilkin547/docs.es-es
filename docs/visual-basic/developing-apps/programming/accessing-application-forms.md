---
title: "Acceso a los formularios de aplicaciones (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "formularios de la aplicación, obtener acceso"
  - "formularios, obtener acceso a todos los abiertos"
  - "formularios, obtener acceso entre sí"
  - "formularios, comunicación entre"
  - "My.Forms (objeto)"
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Acceso a los formularios de aplicaciones (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El objeto `My.Forms` proporciona una manera fácil de tener acceso a una instancia de cada Windows Form declarado en el proyecto de la aplicación.  También puede utilizar propiedades del objeto `My.Application` para tener acceso a la pantalla de presentación y el formulario principal de la aplicación y para obtener una lista de los formularios abiertos de la aplicación.  
  
## Tareas  
 En la tabla siguiente, se muestran algunos ejemplos de cómo obtener acceso a los formularios de una aplicación.  
  
|||  
|-|-|  
|Para|Vea|  
|Tener acceso a un formulario desde otro formulario de una aplicación.|[My.Forms \(Objeto\)](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|Mostrar los títulos de todos los formularios abiertos de la aplicación.|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|Actualizar la pantalla de presentación con información de estado como los inicios de la aplicación.|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>   
 [My.Forms \(Objeto\)](../../../visual-basic/language-reference/objects/my-forms-object.md)