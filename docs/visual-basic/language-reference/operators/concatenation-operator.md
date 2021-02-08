---
description: 'Más información acerca de: &amp; operador (Visual Basic)'
title: Operador &amp;
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: ba7c94805e805c841d05241fef557ca972a19ae9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774101"
---
# <a name="amp-operator-visual-basic"></a>&amp; Operador (Visual Basic)

Genera una concatenación de cadenas de dos expresiones.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Partes  

 `result`  
 Necesario. Cualquier `String` `Object` variable o.  
  
 `expression1`  
 Necesario. Cualquier expresión con un tipo de datos que se amplíe a `String` .  
  
 `expression2`  
 Necesario. Cualquier expresión con un tipo de datos que se amplíe a `String` .  
  
## <a name="remarks"></a>Observaciones  

 Si el tipo de datos de `expression1` o `expression2` no es `String` pero se amplía a `String` , se convierte en `String` . Si uno de los tipos de datos no se amplía a `String` , el compilador genera un error.  
  
 El tipo de datos de `result` es `String` . Si una o ambas expresiones se evalúan como [Nothing](../nothing.md) o tienen un valor de <xref:System.DBNull.Value?displayProperty=nameWithType> , se tratan como una cadena con un valor de "".  
  
> [!NOTE]
> El `&` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
> El carácter de y comercial (&) también se puede usar para identificar variables como tipo `Long` . Para obtener más información, vea [caracteres de tipo](../../programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa el `&` operador para forzar la concatenación de cadenas. El resultado es un valor de cadena que representa la concatenación de los dos operandos de cadena.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [&= (operador)](and-assignment-operator.md)
- [Operadores de concatenación](concatenation-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Operadores de concatenación en Visual Basic](../../programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
