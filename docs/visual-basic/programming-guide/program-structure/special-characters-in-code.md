---
title: "Caracteres especiales en código (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 11c5ef9ad41fc2362d9ba4f2cb5eb5b63a9ca31c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="special-characters-in-code-visual-basic"></a>Caracteres especiales en código (Visual Basic)
En ocasiones tendrá que usar caracteres especiales en el código, es decir, caracteres que no sean alfabéticos o numéricos. Los signos de puntuación y caracteres especiales en el [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] juego de caracteres tienen varias finalidades, desde organizar el texto del programa hasta definir las tareas que realiza el compilador o el programa compilado. No especifican que se deba realizar una operación.  
  
## <a name="parentheses"></a>Paréntesis  
 Utilice paréntesis al definir un procedimiento, como un `Sub` o `Function`. Todas las listas de argumentos de procedimiento deben incluir entre paréntesis. También se utilizan paréntesis para agrupar variables o argumentos en grupos lógicos, especialmente para invalidar el orden predeterminado de prioridad de operador en una expresión compleja. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 Tras la ejecución del código anterior, el valor de `d` es 8,225 y el valor de `e` es 3. El cálculo de `d` utiliza la prioridad predeterminada de `/` sobre `+` y es equivalente a `d = b + (c / a)`. Los paréntesis en el cálculo de `e` alto la prioridad predeterminada.  
  
## <a name="separators"></a>Separadores  
 Los separadores hacen lo que sugiere su nombre: separan dos secciones de código. En [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], el carácter separador es el signo de dos puntos (`:`). Utilice separadores cuando van a incluir varias instrucciones en una sola línea en lugar de líneas separadas. Esto ahorra espacio y mejora la legibilidad del código. En el siguiente ejemplo muestra tres instrucciones separadas por signos de dos puntos.  
  
 [!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 Para obtener más información, consulte [Cómo: salto y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 Los dos puntos (`:`) caracteres también se usan para identificar una etiqueta de instrucción. Para obtener más información, consulte [Cómo: instrucciones de la etiqueta](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## <a name="concatenation"></a>Concatenación  
 Use la `&` operador para *concatenación*, o se vinculan las cadenas. No debe confundirse con el `+` operador, que suma los valores numéricos. Si usas el `+` operador que se va a concatenar al operar en valores numéricos, puede obtener resultados incorrectos. En el siguiente ejemplo se muestra cómo hacerlo.  
  
 [!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 Tras la ejecución del código anterior, el valor de `resultA` es 21,01 y el valor de `resultB` es "10,0111".  
  
## <a name="member-access-operators"></a>Operadores de acceso a miembros  
 Para obtener acceso a un miembro de un tipo, use el punto (`.`) o signo de exclamación (`!`) (operador) entre el nombre de tipo y el nombre del miembro.  
  
### <a name="dot--operator"></a>Punto (.) Operador  
 Use la `.` operador en una clase, estructura, interfaz o enumeración como un operador de acceso de miembro. El miembro puede ser un campo, propiedad, evento o método. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### <a name="exclamation-point--operator"></a>Signo de exclamación (!) Operador  
 Use la `!` operador solo en una clase o interfaz como un operador de acceso de diccionario. La clase o interfaz debe tener una propiedad predeterminada que acepta un único `String` argumento. El identificador que sigue inmediatamente el `!` operador se convierte en el valor del argumento pasado a la propiedad predeterminada como una cadena. En el siguiente ejemplo se muestra cómo hacerlo.  
  
 [!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 Las tres líneas de salida `MsgBox` todos mostrar el valor `32856`. La primera línea utiliza el acceso tradicional a la propiedad `index`, la segunda hace uso del hecho de que `index` es la propiedad predeterminada de la clase `hasDefault`, y la tercera utiliza acceso de diccionario a la clase.  
  
 Tenga en cuenta que el segundo operando de la `!` operador debe ser un identificador válido de Visual Basic no está entre comillas dobles (`" "`). En otras palabras, no se puede utilizar un literal de cadena o una variable de cadena. Cambia ni lo siguiente a la última línea de la `MsgBox` llamada genera un error porque `"X"` es una cadena entre comillas literal.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  Las referencias a colecciones predeterminadas deben ser explícitas. En concreto, no puede usar el `!` operador en una variable en tiempo de ejecución.  
  
 El `!` caracteres también se usan como el `Single` carácter de tipo.  
  
## <a name="see-also"></a>Vea también  
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
