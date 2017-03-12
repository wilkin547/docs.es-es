---
title: "C&#243;mo: Leer la configuraci&#243;n de la aplicaci&#243;n en Visual Basic | Microsoft Docs"
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
  - "configuración de la aplicación, leer"
  - "My.Settings (objeto), leer la configuración de la aplicación"
  - "leer la configuración de la aplicación"
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# C&#243;mo: Leer la configuraci&#243;n de la aplicaci&#243;n en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Puede leer una configuración del usuario teniendo acceso a la propiedad de la configuración en el objeto `My.Settings`.  
  
 El objeto `My.Settings` expone cada configuración como una propiedad.  El nombre de propiedad es igual que el nombre de la configuración y el tipo de propiedad es igual que el tipo de configuración.  El **Ámbito** de configuración indica si la propiedad es de sólo lectura; la propiedad de una configuración de ámbito **Aplicación** es de sólo lectura, mientras que la propiedad de una configuración de ámbito **Usuario** es de lectura y escritura.  Para obtener más información, vea [My.Settings \(Objeto\)](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## Ejemplo  
 En este ejemplo se muestra el valor de la configuración `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/visualbasic/VbVbalrMyResources2/Form1.vb#14)]  
  
 Para que este ejemplo funcione, la aplicación debe tener una configuración `Nickname` de tipo `String`.  Para obtener más información, vea [Administrar la configuración de la aplicación \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
## Vea también  
 [My.Settings \(Objeto\)](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Cómo: Cambiar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Cómo: Conservar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Administrar la configuración de la aplicación \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)