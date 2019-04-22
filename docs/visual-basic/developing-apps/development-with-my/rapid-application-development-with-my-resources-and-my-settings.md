---
title: Desarrollo rápido de aplicaciones con My.Resources y My.Settings (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 4a9021af23200323397cc49fa1a44a0cc48b5a1d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816712"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Desarrollo rápido de aplicaciones con My.Resources y My.Settings (Visual Basic)
La `My.Resources` objeto proporciona acceso a recursos de la aplicación y le permite recuperar dinámicamente los recursos de su aplicación.  
  
## <a name="retrieving-resources"></a>Recuperar recursos  
 Un número de recursos, como cadenas, iconos, imágenes y archivos de audio se puede recuperar mediante el `My.Resources` objeto. Por ejemplo, puede tener acceso a archivos de recursos específicos de la referencia cultural de la aplicación. En el ejemplo siguiente se establece el icono del formulario en el icono denominado `Form1Icon` almacenados en el archivo de recursos de la aplicación.  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 La `My.Resources` objeto expone sólo recursos globales. No proporciona acceso a los archivos de recursos asociados con los formularios. Debe tener acceso a los recursos de formulario desde el formulario.  
  
 De forma similar, la `My.Settings` objeto proporciona acceso a la configuración de la aplicación y permite almacenar y recuperar valores de propiedad y otra información para la aplicación de forma dinámica. Para obtener más información, consulte [My.Resources (objeto)](../../../visual-basic/language-reference/objects/my-resources-object.md) y [My.Settings (objeto)](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>Vea también

- [My.Resources (objeto)](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [My.Settings (objeto)](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Acceso a la configuración de la aplicación](../../../visual-basic/developing-apps/programming/app-settings/index.md)
