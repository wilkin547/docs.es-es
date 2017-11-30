---
title: "Desarrollo rápido de aplicaciones con My.Resources y My.Settings (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1657febf935560ff4c8dd2f54b10fdcb2254891f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Desarrollo rápido de aplicaciones con My.Resources y My.Settings (Visual Basic)
La `My.Resources` objeto proporciona acceso a los recursos de la aplicación y permite recuperar dinámicamente los recursos de la aplicación.  
  
## <a name="retrieving-resources"></a>Recuperar recursos  
 Un número de recursos, como archivos de audio, iconos, imágenes y cadenas se puede recuperar mediante el `My.Resources` objeto. Por ejemplo, puede tener acceso a archivos de recursos específicos de la referencia cultural de la aplicación. En el ejemplo siguiente se establece el icono del formulario en el icono denominado `Form1Icon` almacenados en el archivo de recursos de la aplicación.  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 La `My.Resources` objeto expone sólo recursos globales. No proporciona acceso a los archivos de recursos asociados con los formularios. Debe tener acceso a los recursos de formulario desde el formulario. Para obtener más información, consulte [Tutorial: Adaptar Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5).  
  
 De forma similar, la `My.Settings` objeto proporciona acceso a la configuración de la aplicación y permite almacenar y recuperar valores de propiedad y otra información para la aplicación de forma dinámica. Para obtener más información, consulte [My.Resources (objeto)](../../../visual-basic/language-reference/objects/my-resources-object.md) y [My.Settings (objeto)](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>Vea también  
 [My.Resources (objeto)](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [My.Settings (objeto)](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [Acceso a la configuración de la aplicación](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)
