---
description: 'Más información acerca de: Procedimiento: para leer la configuración de la aplicación en Visual Basic'
title: Procedimiento para leer la configuración de la aplicación
ms.date: 07/20/2015
helpviewer_keywords:
- reading application settings
- My.Settings object [Visual Basic], reading application settings
- application settings [Visual Basic], reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
ms.openlocfilehash: 30b5a3b0cdf3565fc8c1f0dfa19e7717a714c350
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797827"
---
# <a name="how-to-read-application-settings-in-visual-basic"></a>Cómo: Leer la configuración de la aplicación en Visual Basic

Puede leer la configuración de un usuario accediendo a la propiedad de configuración del objeto `My.Settings`.  
  
 El objeto `My.Settings` expone cada configuración como una propiedad. El nombre de propiedad es el mismo que el nombre de la configuración y el tipo de propiedad es el mismo que el tipo de configuración. El **Ámbito** de la configuración indica si la propiedad es de solo lectura. La propiedad de una configuración con ámbito **Aplicación** es de solo lectura, mientras que la propiedad de una configuración con ámbito **Usuario** es de lectura y escritura. Para obtener más información, vea [My.Settings (Objeto)](../../../language-reference/objects/my-settings-object.md).  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se muestra el valor de la configuración `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 Para que este ejemplo funcione, la aplicación debe tener una configuración `Nickname` de tipo `String`. Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="see-also"></a>Vea también

- [My.Settings (objeto)](../../../language-reference/objects/my-settings-object.md)
- [Cómo: Cambiar la configuración del usuario en Visual Basic](how-to-change-user-settings.md)
- [Cómo: Conservar la configuración del usuario en Visual Basic](how-to-persist-user-settings.md)
- [Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic](how-to-create-property-grids-for-user-settings.md)
- [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
