---
title: + Operador
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: 12c14b3be0562a31470ddbd2d5489ccdbdf3b62b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350292"
---
# <a name="-operator-visual-basic"></a>+ (Operador, Visual Basic)
Suma dos números o devuelve el valor positivo de una expresión numérica. También se puede utilizar para concatenar dos expresiones de cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb
expression1 + expression2
```
  
o

```vb  
+expression1  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`expression1`|Obligatorio. Cualquier expresión numérica o de cadena.|  
|`expression2`|Obligatorio a menos que el operador de `+` calcule un valor negativo. Cualquier expresión numérica o de cadena.|  
  
## <a name="result"></a>Resultado  
 Si `expression1` y `expression2` son ambos numéricos, el resultado es su suma aritmética.  
  
 Si `expression2` está ausente, el operador de `+` es el operador *unario* de identidad para el valor sin modificar de una expresión. En este sentido, la operación consiste en conservar el signo de `expression1`, por lo que el resultado es negativo si `expression1` es negativo.  
  
 Si `expression1` y `expression2` son ambas cadenas, el resultado es la concatenación de sus valores.  
  
 Si `expression1` y `expression2` son de tipos mixtos, la acción tomada depende de sus tipos, su contenido y la configuración de la [instrucción Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md). Para obtener más información, vea las tablas de "Comentarios".  
  
## <a name="supported-types"></a>Tipos admitidos  
 Todos los tipos numéricos, incluidos los tipos de punto flotante y sin signo y `Decimal`, y `String`.  
  
## <a name="remarks"></a>Comentarios  
 En general, `+` realiza una suma aritmética siempre que sea posible y concatena solo cuando ambas expresiones son cadenas.  
  
 Si ninguna de las expresiones es una `Object`, Visual Basic realiza las acciones siguientes.  
  
|Tipos de datos de expresiones|Acción por el compilador|  
|---|---|  
|Ambas expresiones son tipos de datos numéricos (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`o `Double`)|Agregar. El tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`. Vea las tablas "aritmética de enteros" en [tipos de datos de resultados de operadores](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Ambas expresiones son de tipo `String`|Concatenar.|  
|Una expresión es un tipo de datos numérico y la otra es una cadena|Si `Option Strict` se `On`, genere un error del compilador.<br /><br /> Si `Option Strict` es `Off`, convierta implícitamente el `String` en `Double` y agregue.<br /><br /> Si el `String` no se puede convertir en `Double`, inicie una excepción <xref:System.InvalidCastException>.|  
|Una expresión es un tipo de datos numérico y la otra no es [nada](../../../visual-basic/language-reference/nothing.md)|Agregue, con `Nothing` valor cero.|  
|Una expresión es una cadena y la otra es `Nothing`|Concatenate, con `Nothing` valor como "".|  
  
 Si una expresión es una expresión de `Object`, Visual Basic realiza las acciones siguientes.  
  
|Tipos de datos de expresiones|Acción por el compilador|  
|---|---|  
|`Object` expresión contiene un valor numérico y el otro es un tipo de datos numérico|Si `Option Strict` se `On`, genere un error del compilador.<br /><br /> Si `Option Strict` se `Off`, agregue.|  
|`Object` expresión contiene un valor numérico y el otro es de tipo `String`|Si `Option Strict` se `On`, genere un error del compilador.<br /><br /> Si `Option Strict` es `Off`, convierta implícitamente el `String` en `Double` y agregue.<br /><br /> Si el `String` no se puede convertir en `Double`, inicie una excepción <xref:System.InvalidCastException>.|  
|`Object` expresión contiene una cadena y la otra es un tipo de datos numérico|Si `Option Strict` se `On`, genere un error del compilador.<br /><br /> Si `Option Strict` es `Off`, convierta implícitamente la cadena `Object` en `Double` y agregue.<br /><br /> Si el `Object` de cadena no se puede convertir en `Double`, inicie una excepción <xref:System.InvalidCastException>.|  
|`Object` expresión contiene una cadena y la otra es de tipo `String`|Si `Option Strict` se `On`, genere un error del compilador.<br /><br /> Si `Option Strict` es `Off`, convierta implícitamente `Object` en `String` y concatene.|  
  
 Si ambas expresiones son expresiones `Object`, Visual Basic realiza las siguientes acciones (solo`Option Strict Off`).  
  
|Tipos de datos de expresiones|Acción por el compilador|  
|---|---|  
|Ambas expresiones de `Object` contienen valores numéricos|Agregar.|  
|Ambas expresiones `Object` son de tipo `String`|Concatenar.|  
|Una expresión `Object` contiene un valor numérico y la otra contiene una cadena|Convierta implícitamente el `Object` de cadena en `Double` y agregue.<br /><br /> Si el `Object` de cadena no se puede convertir en un valor numérico, inicie una excepción <xref:System.InvalidCastException>.|  
  
 Si `Object` expresión se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md) o <xref:System.DBNull>, el operador de `+` lo trata como un `String` con un valor de "".  
  
> [!NOTE]
> Al utilizar el operador `+`, es posible que no pueda determinar si se producirá la concatenación de cadenas o de suma. Use el operador `&` para la concatenación para eliminar la ambigüedad y proporcionar código autodocumentado.  
  
## <a name="overloading"></a>Sobrecarga  
 El operador de `+` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `+` para agregar números. Si los operandos son numéricos, Visual Basic calcula el resultado aritmético. El resultado aritmético representa la suma de los dos operandos.  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 También puede usar el operador `+` para concatenar cadenas. Si los operandos son ambas cadenas, Visual Basic las concatena. El resultado de la concatenación representa una sola cadena formada por el contenido de los dos operandos uno tras otro.  
  
 Si los operandos son de tipos mixtos, el resultado depende de la configuración de la [instrucción Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md). En el ejemplo siguiente se muestra el resultado cuando se `On``Option Strict`.  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 En el ejemplo siguiente se muestra el resultado cuando se `Off``Option Strict`.  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 Para eliminar la ambigüedad, debe utilizar el operador `&` en lugar de `+` para la concatenación.  
  
## <a name="see-also"></a>Vea también

- [Operador &](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [Operadores de concatenación](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
