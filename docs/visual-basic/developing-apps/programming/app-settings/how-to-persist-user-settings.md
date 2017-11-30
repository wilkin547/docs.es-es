---
title: "Cómo: Conservar la configuración del usuario en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], persisting user settings
- persistence [Visual Basic], persisting user settings [Visual Basic]
- user settings [Visual Basic], persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e1cf424a4e587818a8e2766a5e27c084010c084c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-persist-user-settings-in-visual-basic"></a>Cómo: Conservar la configuración del usuario en Visual Basic
Puede usar el método `My.Settings.Save` para conservar los cambios en la configuración del usuario.  
  
 Normalmente, las aplicaciones están diseñadas para conservar los cambios en la configuración de usuario cuando se cierra la aplicación. La causa de esto es que guardar la configuración puede tardar varios segundos, en función de varios factores.  
  
 Para obtener más información, vea [My.Settings (Objeto)](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Aunque puede cambiar y guardar los valores de configuración con ámbito de usuario en tiempo de ejecución, la configuración con ámbito de aplicación es de solo lectura y no se puede cambiar mediante programación. Puede cambiar la configuración con ámbito de aplicación al crear la aplicación mediante el **Diseñador de proyectos** o editando el archivo de configuración de la aplicación. Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo cambia el valor de la configuración de usuario `LastChanged` y guarda el cambio llamando al método `My.Settings.Save`.  
  
 [!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-persist-user-settings_1.vb)]  
  
 Para que este ejemplo funcione, la aplicación debe tener una configuración de usuario `LastChanged`, de tipo `Date`. Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="see-also"></a>Vea también  
 [My.Settings (objeto)](../../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [Cómo: Leer la configuración de la aplicación en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [Cómo: Cambiar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
