---
description: 'Más información acerca de: Realizar tareas con My.Application, My.Computer y My.User (Visual Basic)'
title: Realizar tareas con My.Application, My.Computer y My.User
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 46f8e4654008b38ae98b4c61f5a0c54506e42fcd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797944"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a>Realizar tareas con My.Application, My.Computer y My.User (Visual Basic)

Los tres objetos centrales de `My` que proporcionan acceso a información y funciones de uso frecuente son `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>) y `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>). Puede usar estos objetos para acceder a información relacionada con la aplicación actual, el equipo en el que está instalada la aplicación o el usuario actual de la aplicación, respectivamente.  
  
## <a name="myapplication-mycomputer-and-myuser"></a>My.Application, My.Computer y My.User  

 En los ejemplos siguientes se muestra cómo se puede recuperar información mediante `My`.  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 Además de recuperar información, los miembros expuestos a través de estos tres objetos también permiten ejecutar métodos relacionados con ese objeto. Por ejemplo, puede acceder a diversos métodos para manipular archivos o actualizar el registro a través de `My.Computer`.  
  
 La E/S de archivos es mucho más sencilla y rápida con `My`, que incluye una variedad de métodos y propiedades para manipular archivos, directorios y unidades. El objeto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> permite leer archivos estructurados de gran tamaño que tienen campos delimitados o de ancho fijo. En este ejemplo se abre el objeto `reader` `TextFieldParser` y se usa para leer desde `C:\TestFolder1\test1.txt`.  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 `My.Application` permite cambiar la referencia cultural de la aplicación. En el ejemplo siguiente se muestra cómo llamar a este método.  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Cómo My depende del tipo de proyecto](how-my-depends-on-project-type.md)
