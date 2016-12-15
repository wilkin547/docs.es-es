---
title: "C&#243;mo: Cambiar la configuraci&#243;n del usuario en Visual Basic | Microsoft Docs"
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
  - "ejemplos [Visual Basic], cambiar la configuración del usuario"
  - "My.Settings (objeto), cambiar la configuración del usuario"
  - "configuración del usuario"
  - "configuración del usuario, cambiar en Visual Basic"
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Cambiar la configuraci&#243;n del usuario en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Puede cambiar una configuración de usuario asignando un nuevo valor a la propiedad de configuración en el objeto `My.Settings`.  
  
 El objeto `My.Settings` expone cada configuración como una propiedad.  El nombre de propiedad es igual que el nombre de la configuración y el tipo de propiedad es igual que el tipo de configuración.  El **Ámbito** del valor determina si la propiedad es de sólo lectura: la propiedad de un ajuste de ámbito de **Aplicación** es de sólo lectura, mientras que la propiedad de un ajuste de ámbito de **Usuario** es de lectura\-escritura.  Para obtener más información, vea [My.Settings \(Objeto\)](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Aunque puede cambiar y guardar los valores de la configuración de ámbito de usuario en tiempo de ejecución, esta configuración es de sólo lectura y no se puede cambiar mediante programación.  Puede cambiar la configuración de ámbito de la aplicación al crearla, mediante el **Diseñador de proyectos** o editando el archivo de configuración de la aplicación.  Para obtener más información, vea [Administrar la configuración de la aplicación \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
## Ejemplo  
 Este ejemplo cambia el valor de usuario `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#7](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-change-user-settings_1.vb)]  
  
 Para que funcione este ejemplo, su aplicación debe tener un ajuste de usuario `Nickname`, de tipo `String`.  
  
 La aplicación guarda la configuración del usuario cuando se cierra.  Para guardar inmediatamente la configuración, llame al método `My.Settings.Save`.  Para obtener más información, vea [Cómo: Conservar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).  
  
## Vea también  
 [My.Settings \(Objeto\)](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Cómo: Leer la configuración de la aplicación en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Cómo: Conservar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Administrar la configuración de la aplicación \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)