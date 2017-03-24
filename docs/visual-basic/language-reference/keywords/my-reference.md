---
title: "Referencia de My (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Mi característica"
  - "Mi referencia"
ms.assetid: 6f803bd7-21ff-4569-b1fe-b00a6678b1e3
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Referencia de My (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La característica `My` facilita y agiliza la programación, ya que proporciona acceso intuitivo a los métodos, propiedades y eventos de uso frecuente.  Esta tabla muestra los objetos contenidos en `My` y las acciones que se pueden realizar con cada uno.  
  
|**Acción**|**Objeto.**|  
|----------------|-----------------|  
|Tener acceso a información y servicios de la aplicación.|El objeto `My.Application` consta de las siguientes clases:<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> proporciona miembros que están disponibles en todos los proyectos.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> proporciona miembros que están disponibles en las aplicaciones de Windows Forms.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> proporciona los miembros que están disponibles en las aplicaciones de consola.|  
|Tener acceso al equipo host y sus recursos, servicios y datos.|`My.Computer` \(<xref:Microsoft.VisualBasic.Devices.Computer>\)|  
|Tener acceso a los formularios del proyecto actual.|[My.Forms \(Objeto\)](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|Tener acceso al registro de aplicaciones.|`My.Application.Log` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>\)|  
|Tener acceso a la solicitud de Web actual.|[My.Request \(Objeto\)](../../../visual-basic/language-reference/objects/my-request-object.md)|  
|Tener acceso a los elementos de recurso.|[My.Resources \(Objeto\)](../../../visual-basic/language-reference/objects/my-resources-object.md)|  
|Tener acceso a la respuesta de Web actual.|[My.Response \(Objeto\)](../../../visual-basic/language-reference/objects/my-response-object.md)|  
|Tener acceso a la configuración de nivel de usuario y aplicación.|[My.Settings \(Objeto\)](../../../visual-basic/language-reference/objects/my-settings-object.md)|  
|Tener acceso al contexto de seguridad del usuario actual.|`My.User` \(<xref:Microsoft.VisualBasic.ApplicationServices.User>\)|  
|Tener acceso a servicios Web XML a los que hace referencia el proyecto actual.|[My.WebServices \(Objeto\)](../../../visual-basic/language-reference/objects/my-webservices-object.md)|  
  
## Vea también  
 [Información general sobre el modelo de aplicaciones de Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)   
 [Desarrollo con la función My](../../../visual-basic/developing-apps/development-with-my/index.md)