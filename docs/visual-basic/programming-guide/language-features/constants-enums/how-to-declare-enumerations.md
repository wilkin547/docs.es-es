---
title: "Cómo: Declarar enumeraciones (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 938550ebbfcf099729db3de96b809549cb234d81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Cómo: Declarar enumeraciones (Visual Basic)
Cree una enumeración con el `Enum` instrucción en la sección de declaraciones de una clase o módulo. No se puede declarar una enumeración dentro de un método. Para especificar el nivel de acceso adecuado, utilice `Private`, `Protected`, `Friend`, o `Public`.  
  
 Un `Enum` tipo tiene un nombre, un tipo subyacente y un conjunto de campos, cada uno de los cuales representa una constante. El nombre debe ser un calificador de Visual Basic .NET válido. El tipo subyacente debe ser uno de los tipos de enteros:`Byte`, `Short`, `Long` o `Integer`. `Integer` es el valor predeterminado. Las enumeraciones son siempre establecimiento inflexible de tipos y no son intercambiables con tipos de números enteros.  
  
 Las enumeraciones no pueden tener valores de punto flotante. Si se asigna un valor de punto flotante con una enumeración `Option Strict On`, obtendrá un error del compilador. Si `Option Strict` es `Off`, el valor se convierte automáticamente en el `Enum` tipo.  
  
 Para obtener información sobre nombres y cómo usar el `Imports` instrucción para asegurarse de calificación de nombres no es necesario, consulte [enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Para declarar una enumeración  
  
1.  Escriba una declaración que incluya un nivel de acceso del código, el `Enum` palabra clave y un nombre válido, como en los ejemplos siguientes, cada uno de los cuales declara otra `Enum`.  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  Defina las constantes en la enumeración. De forma predeterminada, la primera constante de una enumeración se inicializa en `0`, y constantes subsiguientes se inicializan con un valor de la constante anterior más uno. Por ejemplo, la siguiente enumeración, `Days`, contiene una constante denominada `Sunday` con el valor `0`, una constante denominada `Monday` con el valor `1`, una constante denominada `Tuesday` con el valor de `2`, y así sucesivamente.  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  Puede asignar explícitamente valores a constantes en una enumeración mediante una instrucción de asignación. Puede asignar cualquier valor entero, incluidos los números negativos. Por ejemplo, puede que desee constantes con valores menores que cero para representar las condiciones de error. En la siguiente enumeración, la constante `Invalid` no se asigna explícitamente el valor `–1`y la constante `Sunday` se asigna el valor `0`. Dado que es la primera constante de la enumeración, `Saturday` también se inicializa con el valor `0`. El valor de `Monday` es `1` (uno más que el valor de `Sunday`); el valor de `Tuesday` es `2`, y así sucesivamente.  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Para declarar una enumeración como un tipo explícito  
  
-   Especificar el tipo de la enumeración mediante el `As` cláusula, tal como se muestra en el ejemplo siguiente.  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Hacer referencia al miembro de una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Cómo: recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Determinar la cadena asociada a un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Información general sobre las constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)
