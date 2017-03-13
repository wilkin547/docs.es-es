---
title: "C&#243;mo: Conservar la configuraci&#243;n del usuario en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Settings (objeto), conservar la configuración del usuario"
  - "persistencia, conservar la configuración del usuario [Visual Basic]"
  - "configuración del usuario, conservar"
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# C&#243;mo: Conservar la configuraci&#243;n del usuario en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Puede utilizar el método `My.Settings.Save` para conservar los cambios efectuados en la configuración del usuario.  
  
 Normalmente, las aplicaciones se diseñan para que conserven los cambios realizados en la configuración del usuario cuando se cierra la aplicación.  Esto es así porque, dependiendo de varios factores, se puede tardar varios segundos en guardar la configuración.  
  
 Para obtener más información, vea [My.Settings \(Objeto\)](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Aunque puede cambiar y guardar los valores de la configuración de ámbito de usuario en tiempo de ejecución, esta configuración es de sólo lectura y no se puede cambiar mediante programación.  Puede cambiar la configuración de ámbito de la aplicación al crearla, mediante el **Diseñador de proyectos**, o editando el archivo de configuración de la aplicación.  Para obtener más información, vea [Administrar la configuración de la aplicación \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
## Ejemplo  
 Este ejemplo cambia el valor de configuración de usuario `LastChanged` y guarda ese cambio llamando al método `My.Settings.Save`.  
  
 [!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-persist-user-settings_1.vb)]  
  
 Para que funcione este ejemplo, su aplicación debe tener un ajuste de usuario `LastChanged`, de tipo `Date`.  Para obtener más información, vea [Administrar la configuración de la aplicación \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
## Vea también  
 [My.Settings \(Objeto\)](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Cómo: Leer la configuración de la aplicación en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Cómo: Cambiar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Administrar la configuración de la aplicación \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)