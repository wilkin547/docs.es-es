---
title: SByte (Tipo de datos, Visual Basic)
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94ab72b2ac2678640697e3cfab426e5a7d6d889a
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "43257401"
---
# <a name="sbyte-data-type-visual-basic"></a>Tipo de datos SByte (Visual Basic)

Contiene enteros de 8 bits (1-bytes) comprendidos en el valor de -128 a 127.  
  
## <a name="remarks"></a>Comentarios

Use la `SByte` tipo de datos para contener valores enteros que no requieren el ancho completo de datos de `Integer` o incluso el ancho de la mitad de los datos de `Short`. En algunos casos, common language runtime puede empaquetar su `SByte` variables juntas y ahorrar consumo de memoria.

El valor predeterminado de `SByte` es 0.

## <a name="literal-assignments"></a>Asignaciones de literales
  
Puede declarar e inicializar un `SByte` variable mediante la asignación de un literal decimal, un literal hexadecimal, un literal octal, o (a partir de 2017 Visual Basic) un literal binario.

En el ejemplo siguiente, los enteros que equivalen a -102 que se representan como decimal, hexadecimal, literales binarios y se asignan a `SByte` valores. En este ejemplo requiere que se compilen con la `/removeintchecks` modificador del compilador.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como en el ejemplo siguiente se muestra.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

A partir de Visual Basic 15.5, también puede usar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales. Por ejemplo:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Si el literal entero está fuera del intervalo de `SByte` (es decir, si es inferior a <xref:System.SByte.MinValue?displayProperty=nameWithType> o mayor que <xref:System.SByte.MaxValue?displayProperty=nameWithType>, se produce un error de compilación. Cuando un literal entero no tiene sufijo, un [entero](integer-data-type.md) se infiere. Si el literal entero está fuera del intervalo de la `Integer` tipo, un [largo](long-data-type.md) se infiere. Esto significa que, en los ejemplos anteriores, los literales numéricos `0x9A` y `0b10011010` se interpretan como enteros de 32 bits con signo con un valor de 156, que supera <xref:System.SByte.MaxValue?displayProperty=nameWithType>. Para compilar correctamente el código como éste que asigna un entero que no sea decimal en un `SByte`, puede hacer lo siguiente:

- Deshabilitar las comprobaciones de límites de enteros a la compilación con el `/removeintchecks` modificador del compilador.

- Use un [carácter de tipo](../../programming-guide\language-features\data-types/type-characters.md) para definir explícitamente el valor literal que se desea asignar a la `SByte`. En el ejemplo siguiente se asigna un literal negativo `Short` valor a un `SByte`. Tenga en cuenta que, para los números negativos, se debe establecer el bit de orden superior de la palabra de orden superior de un literal numérico. En el caso de nuestro ejemplo, esto es de tipo bit 15 del literal `Short` valor.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Sugerencias de programación
  
-   **Conformidad con CLS.** El `SByte` es de tipo de datos no forma parte de la [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código conforme a CLS no puede utilizar un componente que lo utiliza.

-   **Ampliación.** El `SByte` tipo de datos se amplía a `Short`, `Integer`, `Long`, `Decimal`, `Single`, y `Double`. Esto significa que se puede convertir `SByte` a cualquiera de estos tipos sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.
  
-   **Caracteres de tipo.** `SByte` no tiene ningún carácter de tipo literal o un carácter de tipo identificador.  
  
-   **Tipo de marco de trabajo.** El tipo correspondiente en .NET Framework es la estructura <xref:System.SByte?displayProperty=nameWithType>.
  
## <a name="see-also"></a>Vea también

 <xref:System.SByte?displayProperty=nameWithType>  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Short (tipo de datos)](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [Integer (tipo de datos)](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Long (tipo de datos)](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
