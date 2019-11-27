---
title: Desarrollo rápido de aplicaciones con My.Resources y My.Settings
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: ce9a5bf76ba3132f58aa40227a145d8b5bf1591d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349263"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Desarrollo rápido de aplicaciones con My.Resources y My.Settings (Visual Basic)

El objeto `My.Resources` proporciona acceso a los recursos de la aplicación y permite recuperar dinámicamente los recursos de la aplicación.  
  
## <a name="retrieving-resources"></a>Recuperar recursos  

 Se puede recuperar una serie de recursos, como archivos de audio, iconos, imágenes y cadenas, a través del objeto `My.Resources`. Por ejemplo, puede tener acceso a los archivos de recursos específicos de la referencia cultural de la aplicación. En el ejemplo siguiente se establece el icono del formulario en el icono denominado `Form1Icon` almacenado en el archivo de recursos de la aplicación.  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 El objeto `My.Resources` expone solo recursos globales. No proporciona acceso a los archivos de recursos asociados a los formularios. Debe tener acceso a los recursos de formulario desde el formulario.  
  
 De forma similar, el objeto `My.Settings` proporciona acceso a la configuración de la aplicación y le permite almacenar y recuperar dinámicamente la configuración de propiedades y otra información de la aplicación. Para obtener más información, vea [My. Resources (objeto](../../../visual-basic/language-reference/objects/my-resources-object.md) ) y [My. Settings (objeto](../../../visual-basic/language-reference/objects/my-settings-object.md)).  
  
## <a name="see-also"></a>Vea también

- [My.Resources (objeto)](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [My.Settings (objeto)](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Accessing Application Settings](../../../visual-basic/developing-apps/programming/app-settings/index.md)
