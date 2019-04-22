---
title: Caracteres especiales en código (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 65fcd10521742e287c7934080b3352a06668df7a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835562"
---
# <a name="special-characters-in-code-visual-basic"></a>Caracteres especiales en código (Visual Basic)
A veces es necesario usar caracteres especiales en el código, es decir, los caracteres que no sean alfabéticos o numéricos. La puntuación y caracteres especiales en el juego de caracteres de Visual Basic tienen varias finalidades, desde organizar el texto del programa hasta definir las tareas que realiza el compilador o el programa compilado. No especifican que se deba realizar una operación.  
  
## <a name="parentheses"></a>Paréntesis  
 Utilice paréntesis al definir un procedimiento, como un `Sub` o `Function`. Todas las listas de argumentos de procedimiento debe ir entre paréntesis. También se utilice paréntesis para agrupar las variables o argumentos en grupos lógicos, especialmente para invalidar el orden predeterminado de prioridad de operador en una expresión compleja. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 Tras la ejecución del código anterior, el valor de `d` es 8,225 y el valor de `e` es 3. El cálculo para `d` utiliza la prioridad predeterminada de `/` sobre `+` y es equivalente a `d = b + (c / a)`. Los paréntesis en el cálculo para `e` la prioridad predeterminada.  
  
## <a name="separators"></a>Separadores  
 Separadores hacen lo que sugiere su nombre: separan dos secciones de código. En Visual Basic, el carácter separador es los dos puntos (`:`). Utilice separadores cuando desee incluir varias instrucciones en una sola línea en lugar de líneas independientes. Esto ahorra espacio y mejora la legibilidad del código. El ejemplo siguiente muestra tres instrucciones separadas por signos de dos puntos.  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 Para obtener más información, vea [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 Los dos puntos (`:`) caracteres también se usan para identificar una etiqueta de instrucción. Para obtener más información, vea [Cómo: Etiquetar instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## <a name="concatenation"></a>Concatenación  
 Use la `&` operador para *concatenación*, o vincular cadenas conjuntamente. No lo confunda con el `+` operador, que suma valores numéricos. Si usas el `+` para concatenar cuando se opera en valores numéricos, puede obtener resultados incorrectos. En el siguiente ejemplo se muestra cómo hacerlo.  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 Tras la ejecución del código anterior, el valor de `resultA` es 21,01 y el valor de `resultB` es "10,0111".  
  
## <a name="member-access-operators"></a>Operadores de acceso a miembros  
 Para obtener acceso a un miembro de un tipo, usa el punto (`.`) o signo de exclamación (`!`) operador entre el nombre de tipo y el nombre del miembro.  
  
### <a name="dot--operator"></a>Punto (.) Operador  
 Use el `.` operador en una clase, estructura, interfaz o enumeración como un operador de acceso de miembro. El miembro puede ser un campo, propiedad, evento o método. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a>Signo de exclamación (!) Operador  
 Use el `!` operador solo en una clase o interfaz como un operador de acceso de diccionario. La clase o interfaz debe tener una propiedad predeterminada que acepta un único `String` argumento. El identificador que sigue inmediatamente el `!` operador se convierte en el valor del argumento pasado a la propiedad predeterminada como una cadena. En el siguiente ejemplo se muestra cómo hacerlo.  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 Las tres líneas de salida `MsgBox` todos mostrar el valor `32856`. La primera línea usa el acceso a propiedad tradicional `index`, el segundo usa el hecho de que `index` es la propiedad predeterminada de la clase `hasDefault`, y la tercera usa el acceso al diccionario para la clase.  
  
 Tenga en cuenta que el segundo operando de la `!` operador debe ser un identificador válido de Visual Basic no está entrecomillado comillas dobles (`" "`). En otras palabras, no se puede utilizar un literal de cadena o una variable de cadena. Los siguientes elementos cambiar a la última línea de la `MsgBox` llamada genera un error porque `"X"` es una cadena incluida literal.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  Las referencias a colecciones predeterminadas deben ser explícitas. En concreto, no puede usar el `!` operador en una variable en tiempo de ejecución.  
  
 El `!` carácter también se usa como el `Single` carácter de tipo.  
  
## <a name="see-also"></a>Vea también

- [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
