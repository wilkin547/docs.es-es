---
title: "How To: Create a New Setting at Design Time | Microsoft Docs"
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
  - "application settings [Windows Forms], design time"
  - "application settings [Windows Forms], creating"
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# How To: Create a New Setting at Design Time
Puede crear un nuevo valor de configuración en tiempo de diseño mediante el diseñador de configuración.  El diseñador de configuración es una interfaz con forma de cuadrícula que permite crear nuevos valores de configuración y especificar las propiedades de esos valores.  Debe especificar el Nombre, el Valor, el Tipo y el Ámbito de los nuevos valores de configuración.  Una vez creado un valor, se puede tener acceso a él en el código.  
  
### Para crear un nuevo valor de configuración en tiempo de diseño en C\#  
  
1.  En el **Explorador de soluciones**, expanda el nodo **Propiedades** del proyecto.  
  
2.  Haga doble clic en el archivo .settings al que desea agregar un nuevo valor.  El nombre predeterminado de este archivo es Settings.settings.  
  
3.  En el diseñador de configuración, establezca el Nombre, el Valor, el Tipo y el Ámbito del valor de configuración.  Cada fila representa un valor único.  
  
### Para crear un nuevo valor de configuración en tiempo de diseño en Visual Basic  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en el nodo del proyecto y elija **Propiedades**.  
  
2.  En la página **Propiedades**, seleccione la ficha **Configuración**.  
  
3.  En el diseñador de configuración, establezca el Nombre, el Valor, el Tipo y el Ámbito del valor de configuración.  Cada fila representa un valor único.  
  
## Vea también  
 [Using Application Settings and User Settings](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)   
 [How To: Change the Value of an Existing Setting at Design Time](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)