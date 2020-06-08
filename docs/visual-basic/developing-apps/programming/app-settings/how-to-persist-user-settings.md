---
title: Procedimiento para conservar la configuración del usuario
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], persisting user settings
- persistence [Visual Basic], persisting user settings [Visual Basic]
- user settings [Visual Basic], persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
ms.openlocfilehash: 817111060259bdfbbb26d9f8eafeae439e1f651f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410158"
---
# <a name="how-to-persist-user-settings-in-visual-basic"></a>Procedimiento para conservar la configuración del usuario en Visual Basic

Puede usar el método `My.Settings.Save` para conservar los cambios en la configuración del usuario.  
  
 Normalmente, las aplicaciones están diseñadas para conservar los cambios en la configuración de usuario cuando se cierra la aplicación. La causa de esto es que guardar la configuración puede tardar varios segundos, en función de varios factores.  
  
 Para más información, consulte [My.Settings (Objeto)](../../../language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
> Aunque puede cambiar y guardar los valores de configuración con ámbito de usuario en tiempo de ejecución, la configuración con ámbito de aplicación es de solo lectura y no se puede cambiar mediante programación. Puede cambiar la configuración con ámbito de aplicación al crear la aplicación mediante el **Diseñador de proyectos** o editando el archivo de configuración de la aplicación. Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="example"></a>Ejemplo  

 Este ejemplo cambia el valor de la configuración de usuario `LastChanged` y guarda el cambio llamando al método `My.Settings.Save`.  
  
 [!code-vb[VbVbalrMyResources#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#5)]  
  
 Para que este ejemplo funcione, la aplicación debe tener una configuración de usuario `LastChanged`, de tipo `Date`. Para obtener más información, consulte [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="see-also"></a>Vea también

- [My.Settings (objeto)](../../../language-reference/objects/my-settings-object.md)
- [Cómo: Leer la configuración de la aplicación en Visual Basic](how-to-read-application-settings.md)
- [Cómo: Cambiar la configuración del usuario en Visual Basic](how-to-change-user-settings.md)
- [Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic](how-to-create-property-grids-for-user-settings.md)
- [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
