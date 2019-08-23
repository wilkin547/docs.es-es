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
ms.openlocfilehash: 95bef937912e35cd828bf0090b4cf48ccb3290cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962473"
---
# <a name="special-characters-in-code-visual-basic"></a>Caracteres especiales en código (Visual Basic)
A veces, es necesario usar caracteres especiales en el código, es decir, caracteres que no son alfabéticos o numéricos. Los caracteres de puntuación y especiales del juego de caracteres Visual Basic tienen varios usos, desde organizar el texto del programa hasta definir las tareas que realiza el compilador o el programa compilado. No especifican que se deba realizar una operación.  
  
## <a name="parentheses"></a>Paréntesis  
 Use paréntesis al definir un procedimiento, `Sub` como o. `Function` Debe incluir todas las listas de argumentos de procedimientos entre paréntesis. También puede usar paréntesis para colocar variables o argumentos en grupos lógicos, especialmente para reemplazar el orden predeterminado de prioridad de los operadores en una expresión compleja. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 Después de la ejecución del código anterior, el valor `d` de es 8,225 y el valor `e` de es 3. El cálculo de `d` utiliza la prioridad predeterminada de `/` over `+` y es equivalente a `d = b + (c / a)`. Los paréntesis del cálculo para `e` invalidar la prioridad predeterminada.  
  
## <a name="separators"></a>Separadores  
 Los separadores hacen lo que sugiere su nombre: separan secciones de código. En Visual Basic, el carácter separador es el signo`:`de dos puntos (). Utilice separadores cuando desee incluir varias instrucciones en una sola línea en lugar de líneas independientes. Esto ahorra espacio y mejora la legibilidad del código. En el ejemplo siguiente se muestran tres instrucciones separadas por dos puntos.  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 Para obtener más información, consulte [Cómo Interrumpir y combinar instrucciones en](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)el código.  
  
 El carácter de`:`dos puntos () también se usa para identificar una etiqueta de instrucción. Para obtener más información, vea [Cómo: Instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)de etiqueta.  
  
## <a name="concatenation"></a>Concatenación  
 Use el `&` operador parala concatenación o vincule cadenas. No lo confunda con el `+` operador, que suma los valores numéricos. Si usa el `+` operador para concatenar al trabajar con valores numéricos, puede obtener resultados incorrectos. En el siguiente ejemplo se muestra cómo hacerlo.  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 Después de la ejecución del código anterior, el valor `resultA` de es 21,01 y el valor `resultB` de es "10,0111".  
  
## <a name="member-access-operators"></a>Operadores de acceso a miembros  
 Para tener acceso a un miembro de un tipo, se usa el`.`operador de punto () o`!`el signo de exclamación () entre el nombre de tipo y el nombre de miembro.  
  
### <a name="dot--operator"></a>Punto (.) Operador  
 Use el `.` operador en una clase, estructura, interfaz o enumeración como un operador de acceso a miembros. El miembro puede ser un campo, una propiedad, un evento o un método. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a>Signo de exclamación (!) Operador  
 Use el `!` operador solo en una clase o interfaz como operador de acceso a Diccionario. La clase o la interfaz deben tener una propiedad predeterminada que acepte un `String` solo argumento. El identificador que sigue inmediatamente al `!` operador se convierte en el valor de argumento pasado a la propiedad predeterminada como una cadena. En el siguiente ejemplo se muestra cómo hacerlo.  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 Las tres líneas de `MsgBox` salida muestran el valor. `32856` La primera línea usa el acceso tradicional a la `index`propiedad, la segunda hace uso del hecho que `index` es la propiedad predeterminada de la `hasDefault`clase y la tercera utiliza el acceso de diccionario a la clase.  
  
 Tenga en cuenta que el segundo operando del `!` operador debe ser un identificador de Visual Basic válido no incluido entre comillas dobles (`" "`). En otras palabras, no puede usar un literal de cadena o una variable de cadena. El siguiente cambio en la última línea de la `MsgBox` llamada genera un error porque `"X"` es un literal de cadena delimitado.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
> Las referencias a las colecciones predeterminadas deben ser explícitas. En concreto, no se puede utilizar `!` el operador en una variable enlazada en tiempo de ejecución.  
  
 El `!` carácter también se utiliza como carácter `Single` de tipo.  
  
## <a name="see-also"></a>Vea también

- [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
