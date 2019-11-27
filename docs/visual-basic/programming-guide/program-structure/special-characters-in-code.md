---
title: Caracteres especiales en código
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
ms.openlocfilehash: f4ab35b56d48ae86bdb024ffea27735b39decdc2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347265"
---
# <a name="special-characters-in-code-visual-basic"></a>Caracteres especiales en código (Visual Basic)
A veces, es necesario usar caracteres especiales en el código, es decir, caracteres que no son alfabéticos o numéricos. Los caracteres de puntuación y especiales del juego de caracteres Visual Basic tienen varios usos, desde organizar el texto del programa hasta definir las tareas que realiza el compilador o el programa compilado. No especifican que se deba realizar una operación.  
  
## <a name="parentheses"></a>Paréntesis  
 Use paréntesis al definir un procedimiento, como un `Sub` o `Function`. Debe incluir todas las listas de argumentos de procedimientos entre paréntesis. También puede usar paréntesis para colocar variables o argumentos en grupos lógicos, especialmente para reemplazar el orden predeterminado de prioridad de los operadores en una expresión compleja. En el ejemplo siguiente se ilustra esto.  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 Después de la ejecución del código anterior, el valor de `d` es 8,225 y el valor de `e` es 3. El cálculo de `d` utiliza la prioridad predeterminada de `/` sobre `+` y es equivalente a `d = b + (c / a)`. Los paréntesis en el cálculo de `e` invalidan la prioridad predeterminada.  
  
## <a name="separators"></a>Separadores  
 Los separadores hacen lo que sugiere su nombre: separan secciones de código. En Visual Basic, el carácter separador es el signo de dos puntos (`:`). Utilice separadores cuando desee incluir varias instrucciones en una sola línea en lugar de líneas independientes. Esto ahorra espacio y mejora la legibilidad del código. En el ejemplo siguiente se muestran tres instrucciones separadas por dos puntos.  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 Para obtener más información, vea [Cómo: interrumpir y combinar instrucciones en el código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 El carácter de dos puntos (`:`) también se usa para identificar una etiqueta de instrucción. Para obtener más información, vea [Cómo: etiquetar instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## <a name="concatenation"></a>Concatenación  
 Use el operador `&` para la *concatenación*, o vincule cadenas. No lo confunda con el operador `+`, que suma los valores numéricos. Si usa el operador `+` para concatenar al trabajar con valores numéricos, puede obtener resultados incorrectos. En el siguiente ejemplo se muestra cómo hacerlo.  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 Después de la ejecución del código anterior, el valor de `resultA` es 21,01 y el valor de `resultB` es "10,0111".  
  
## <a name="member-access-operators"></a>Operadores de acceso a miembros  
 Para tener acceso a un miembro de un tipo, se usa el operador de punto (`.`) o el signo de exclamación (`!`) entre el nombre del tipo y el nombre del miembro.  
  
### <a name="dot--operator"></a>Punto (.) Operator  
 Use el operador `.` en una clase, estructura, interfaz o enumeración como un operador de acceso a miembros. El miembro puede ser un campo, una propiedad, un evento o un método. En el ejemplo siguiente se ilustra esto.  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a>Signo de exclamación (!) Operator  
 Utilice el operador `!` solo en una clase o interfaz como operador de acceso a Diccionario. La clase o la interfaz deben tener una propiedad predeterminada que acepte un único argumento de `String`. El identificador situado inmediatamente después del operador de `!` se convierte en el valor de argumento que se pasa a la propiedad predeterminada como una cadena. En el siguiente ejemplo se muestra cómo hacerlo.  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 Las tres líneas de salida de `MsgBox` muestran el valor `32856`. La primera línea usa el acceso tradicional al `index`de propiedad, el segundo hace uso del hecho de que `index` es la propiedad predeterminada de la clase `hasDefault`y la tercera utiliza el acceso de diccionario a la clase.  
  
 Tenga en cuenta que el segundo operando del operador `!` debe ser un identificador de Visual Basic válido no incluido entre comillas dobles (`" "`). En otras palabras, no puede usar un literal de cadena o una variable de cadena. El siguiente cambio en la última línea de la llamada `MsgBox` genera un error porque `"X"` es un literal de cadena delimitado.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
> Las referencias a las colecciones predeterminadas deben ser explícitas. En concreto, no se puede utilizar el operador `!` en una variable enlazada en tiempo de ejecución.  
  
 También se usa el carácter `!` como carácter de tipo `Single`.  
  
## <a name="see-also"></a>Vea también

- [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
