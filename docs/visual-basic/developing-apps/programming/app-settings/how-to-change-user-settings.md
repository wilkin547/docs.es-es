---
title: "Cómo: Cambiar la configuración del usuario en Visual Basic | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- user settings, changing in Visual Basic
- user settings
- My.Settings object, changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1637761f313d75e4385c009ca489ae9667cfd2ad
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-change-user-settings-in-visual-basic"></a>Cómo: Cambiar la configuración del usuario en Visual Basic
Puede cambiar una configuración de usuario mediante la asignación de un nuevo valor a la propiedad de la configuración en el objeto `My.Settings`.  
  
 El objeto `My.Settings` expone cada configuración como una propiedad. El nombre de propiedad es el mismo que el nombre de la configuración y el tipo de propiedad es el mismo que el tipo de configuración. El valor **Scope** de la configuración determina si la propiedad es de solo lectura: la propiedad de una configuración con ámbito **Aplicación** es de solo lectura, mientras que la propiedad de una configuración con ámbito **Usuario** es de lectura y escritura. Para obtener más información, vea [My.Settings (Objeto)](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Aunque se pueden cambiar y guardar los valores de configuraciones con ámbito de usuario en tiempo de ejecución, las configuraciones con ámbito de aplicación son de solo lectura y no se puede cambiar mediante programación. Las configuraciones con ámbito de aplicación se pueden cambiar en el momento de crear la aplicación mediante el **Diseñador de proyectos** o a través del archivo de configuración de la aplicación. Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se cambia el valor de la configuración de usuario `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#7](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-change-user-settings_1.vb)]  
  
 Para que funcione este ejemplo, la aplicación debe tener una configuración de usuario `Nickname`, de tipo `String`.  
  
 La aplicación guarda la configuración del usuario cuando se cierra. Para guardar la configuración inmediatamente, llame al método `My.Settings.Save`. Para obtener más información, vea [Cómo: Conservar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).  
  
## <a name="see-also"></a>Vea también  
 [My.Settings (objeto)](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Cómo: Leer la configuración de la aplicación en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Cómo: Conservar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Administrar la configuración de la aplicación (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)
