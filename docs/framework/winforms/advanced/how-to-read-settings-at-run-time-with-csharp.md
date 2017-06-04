---
title: "How To: Read Settings at Run Time With C# | Microsoft Docs"
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
  - "application settings [Windows Forms], reading"
  - "application settings [Windows Forms], run time"
  - "application settings [Windows Forms], C#"
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# How To: Read Settings at Run Time With C# #
Puede leer valores de configuración de aplicación y usuario en tiempo de ejecución a través del objeto Properties.  El objeto Properties expone todos los valores de configuración predeterminados para el proyecto a través del miembro Properties.Settings.Default.  
  
### Para leer valores de configuración en tiempo de ejecución con C\#  
  
-   Acceda a la configuración correspondiente a través del miembro Properties.Settings.Default.   En el ejemplo siguiente, se muestra cómo asignar un valor de configuración con el nombre `myColor` a una propiedad BackColor.  Es necesario que haya creado previamente un archivo de configuración con una configuración denominada `myColor` de tipo `System.Drawing.Color`.  Para obtener información acerca de cómo crear un archivo de configuración, consulte [How To: Create a New Setting at Design Time](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## Vea también  
 [Using Application Settings and User Settings](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [How To: Write User Settings at Run Time with C\#](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)   
 [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)