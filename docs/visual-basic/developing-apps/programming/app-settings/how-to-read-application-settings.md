---
title: Procedimiento para leer la configuración de la aplicación en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- reading application settings
- My.Settings object [Visual Basic], reading application settings
- application settings [Visual Basic], reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
ms.openlocfilehash: 032e06e674f2298d68f879f3ad474c79e3ff02db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659502"
---
# <a name="how-to-read-application-settings-in-visual-basic"></a>Procedimiento para leer la configuración de la aplicación en Visual Basic
Puede leer la configuración de un usuario accediendo a la propiedad de configuración del objeto `My.Settings`.  
  
 El objeto `My.Settings` expone cada configuración como una propiedad. El nombre de propiedad es el mismo que el nombre de la configuración y el tipo de propiedad es el mismo que el tipo de configuración. El **Ámbito** de la configuración indica si la propiedad es de solo lectura. La propiedad de una configuración con ámbito **Aplicación** es de solo lectura, mientras que la propiedad de una configuración con ámbito **Usuario** es de lectura y escritura. Para más información, consulte [My.Settings (Objeto)](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra el valor de la configuración `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-read-application-settings_1.vb)]  
  
 Para que este ejemplo funcione, la aplicación debe tener una configuración `Nickname` de tipo `String`. Para obtener más información, consulte [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="see-also"></a>Vea también
- [My.Settings (objeto)](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Cómo: Cambiar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [Cómo: Conservar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
