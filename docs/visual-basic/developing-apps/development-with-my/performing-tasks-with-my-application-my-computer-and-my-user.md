---
title: Realizar tareas con My.Application, My.Computer y My.User (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 84ac57bf1bcf60664e2b18fed16a3bbe6c03dc68
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "42755013"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a>Realizar tareas con My.Application, My.Computer y My.User (Visual Basic)
La central de tres `My` son objetos que proporcionan acceso a información y datos consultados funcionalidad `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), y `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>). Puede usar estos objetos para tener acceso a información relacionada con la aplicación actual, el equipo que la aplicación está instalada en o el usuario actual de la aplicación, respectivamente.  
  
## <a name="myapplication-mycomputer-and-myuser"></a>My.Application, My.Computer y My.User  
 Los ejemplos siguientes muestran cómo información se puede recuperar mediante `My`.  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_2.vb)]  
  
 Además de la información de recuperación, los miembros que expone a través de estos tres objetos también permiten ejecutar métodos relacionados con ese objeto. Por ejemplo, puede tener acceso a una variedad de métodos para manipular archivos o actualizar el registro a través de `My.Computer`.  
  
 E/S de archivos es mucho más fácil y rápido con `My`, que incluye una variedad de métodos y propiedades para manipular archivos, directorios y unidades. La <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> objeto le permite leer de archivos estructurados grandes delimitados o campos de ancho fijo. Este ejemplo se abre el `TextFieldParser` `reader` y lo usa para leer desde `C:\TestFolder1\test1.txt`.  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_3.vb)]  
  
 `My.Application` permite cambiar la referencia cultural para la aplicación. El ejemplo siguiente muestra cómo se puede llamar a este método.  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [Cómo My depende del tipo de proyecto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
