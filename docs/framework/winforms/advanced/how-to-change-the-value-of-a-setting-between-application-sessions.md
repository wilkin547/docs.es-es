---
title: "How To: Change the Value of a Setting Between Application Sessions | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "application settings [Windows Forms], changing"
  - "application settings [Windows Forms], between application sessions"
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# How To: Change the Value of a Setting Between Application Sessions
A veces es posible que desee cambiar el valor de una opción entre las sesiones de la aplicación una vez compilada e implementada la aplicación.  Por ejemplo, tal vez desee cambiar una cadena de conexión para que señale a la ubicación de la base de datos correcta.  Puesto que las herramientas en tiempo de diseño no están disponibles una vez compilada e implementada la aplicación, debe cambiar manualmente el valor de la opción en el archivo.  
  
### Para cambiar el valor de una opción de configuración entre sesiones de aplicación  
  
1.  Con el Bloc de notas de Microsoft o algún otro editor de texto o XML, abra el archivo .config asociado a su aplicación.  
  
2.  Busque la entrada del valor que desea cambiar.  Debe ser similar a la que se muestra en el siguiente ejemplo.  
  
    ```  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  Escriba un nuevo valor para la opción y guarde el archivo.  
  
## Vea también  
 [Using Application Settings and User Settings](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)