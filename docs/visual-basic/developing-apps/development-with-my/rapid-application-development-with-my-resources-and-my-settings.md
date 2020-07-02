---
title: Desarrollo rápido de aplicaciones con My.Resources y My.Settings
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: fd1ec25582e919b84235502f5921edfbc6e1dade
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990208"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Desarrollo rápido de aplicaciones con My.Resources y My.Settings (Visual Basic)

El objeto `My.Resources` da acceso a los recursos de la aplicación y permite recuperar recursos de la aplicación dinámicamente.  
  
## <a name="retrieving-resources"></a>Recuperar recursos  

 Con el objeto `My.Resources` se pueden recuperar una serie de recursos, como archivos de audio, iconos, imágenes y cadenas. Por ejemplo, permite acceder a los archivos de recursos específicos de la referencia cultural de la aplicación. En el siguiente ejemplo se establece el icono del formulario en el icono denominado `Form1Icon` que está almacenado en el archivo de recursos de la aplicación.  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 El objeto `My.Resources` expone solo recursos globales. No da acceso a los archivos de recursos asociados a los formularios. Acceda a los recursos del formulario desde el formulario.  
  
 De forma similar, el objeto `My.Settings` da acceso a la configuración de la aplicación y permite almacenar y recuperar dinámicamente la configuración de propiedades y otra información de la aplicación. Para más información, vea [My.Resources Object](../../language-reference/objects/my-resources-object.md) y [My.Settings Object](../../language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>Vea también

- [My.Resources (objeto)](../../language-reference/objects/my-resources-object.md)
- [My.Settings (objeto)](../../language-reference/objects/my-settings-object.md)
- [Acceso a la configuración de la aplicación](../programming/app-settings/index.md)
