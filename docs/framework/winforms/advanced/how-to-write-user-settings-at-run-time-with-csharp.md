---
title: "How To: Write User Settings at Run Time with C# | Microsoft Docs"
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
  - "application settings [Windows Forms], run time"
  - "application settings [Windows Forms], writing user settings"
  - "application settings [Windows Forms], C#"
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# How To: Write User Settings at Run Time with C# #
La configuración del ámbito de aplicación es de solo lectura y únicamente se puede cambiar en tiempo de diseño o modificando el archivo .config entre sesiones de aplicación.  Sin embargo, la configuración del ámbito de usuario puede escribirse en tiempo de ejecución, del mismo modo que cambiaría cualquier valor de propiedad.  El nuevo valor se conserva a lo largo de toda la sesión de la aplicación.  Puede conservar los cambios de la configuración entre sesiones de aplicación llamando al método Save.  
  
### Cómo: Escribir y conservar valores de configuración de usuario en tiempo de ejecución con C\#  
  
1.  Acceda a la configuración y asigne un nuevo valor, tal como se muestra en este ejemplo:  
  
    ```  
    // C#  
    Properties.Settings.Default.myColor = Color.AliceBlue;  
    ```  
  
2.  Si desea conservar los cambios de la configuración entre sesiones de aplicación, llame al método Save tal como se muestra en este ejemplo:  
  
    ```  
    // C#  
    Properties.Settings.Default.Save();  
    ```  
  
     La configuración de usuario se guarda en un archivo en una subcarpeta de la carpeta de datos de aplicación oculta local del usuario.  
  
## Vea también  
 [Using Application Settings and User Settings](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [How To: Read Settings at Run Time With C\#](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)   
 [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)