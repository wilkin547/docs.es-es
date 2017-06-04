---
title: "How To: Add Multiple Sets of Settings To Your Application in C# | Microsoft Docs"
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
  - "application settings [Windows Forms], multiple sets"
  - "application settings [Windows Forms], C#"
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# How To: Add Multiple Sets of Settings To Your Application in C# #
En algunas ocasiones, es posible que desee tener varios conjuntos de valores de configuración en una aplicación.  Por ejemplo, si desarrolla una aplicación en la que se espera que un grupo determinado de valores cambie con frecuencia, podría ser conveniente separar todos estos valores en un archivo único para que el archivo se pueda reemplazar en su totalidad sin que el resto de los valores de configuración resulte afectado.  Visual Studio permite agregar varios conjuntos de valores al proyecto.  Se puede tener acceso a conjuntos adicionales de valores de configuración a través del objeto Properties.Settings.  
  
### Para agregar un conjunto adicional de valores de configuración a la aplicación  
  
1.  En el menú **Proyecto**, elija **Agregar nuevo elemento**.  Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.  
  
2.  En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Archivo de configuración**, escriba en un nombre para el archivo y haga clic en **Agregar** para agregar un nuevo archivo de configuración a la solución.  
  
3.  En el **Explorador de soluciones**, arrastre el nuevo archivo de configuración a la carpeta **Propiedades**.  De esta forma, los nuevos valores de configuración estarán disponibles en el código.  
  
4.  Agregue y utilice los valores de este archivo como haría con cualquier otro archivo de configuración.  Puede tener acceso a este grupo de valores a través del objeto Properties.Settings.  
  
## Vea también  
 [Using Application Settings and User Settings](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)