---
title: "Los parámetros de tipo no se pueden utilizar como calificadores"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 58be51e0c05750ee044f0287cde8db037718b4aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a>Los parámetros de tipo no se pueden utilizar como calificadores
Un elemento de programación está calificado con una cadena de calificación que incluye un parámetro de tipo.  
  
 Un parámetro de tipo representa un requisito para un tipo que se va a proporcionar al construir el tipo genérico. No representa un tipo definido concreto. Una cadena de calificación debe incluir solo los elementos que se definen en tiempo de compilación.  
  
 Las instrucciones siguientes pueden generar este error.  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 **Id. de error:** BC32098  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Quite el parámetro de tipo de la cadena de calificación o reemplácelo con un tipo definido.  
  
2.  Si tiene que utilizar un tipo construido para buscar el elemento de programación que se califica, debe utilizar la lógica del programa adicionales.  
  
## <a name="see-also"></a>Vea también  
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)
