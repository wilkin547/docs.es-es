---
title: UShort (Tipo de datos, Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 038aad2c41f655d0699dab33df276132a70e3ede
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46492725"
---
# <a name="ushort-data-type-visual-basic"></a>Tipo de datos UShort (Visual Basic)

Contiene enteros de 16 bits sin signo (2 bytes) cuyo valor oscila de 0 a 65.535.  
  
## <a name="remarks"></a>Comentarios

 Use la `UShort` tipo de datos para contener datos binarios demasiado grandes para `Byte`.  
  
 El valor predeterminado de `UShort` es 0.  

# <a name="literal-assignments"></a>Asignaciones de literales

Puede declarar e inicializar un `UShort` variable mediante la asignación de un literal decimal, un literal hexadecimal, un literal octal, o (a partir de 2017 Visual Basic) un literal binario. Si el literal entero está fuera del intervalo de `UShort` (es decir, si es inferior a <xref:System.UInt16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 65 034 que se representan como decimal, hexadecimal, literales binarios y se asignan a `UShort` valores.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como en el ejemplo siguiente se muestra.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

A partir de Visual Basic 15.5, también puede usar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales. Por ejemplo:

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

También pueden incluir literales numéricos el `US` o `us` [carácter de tipo](../../programming-guide\language-features\data-types/type-characters.md) para denotar el `UShort` tipo de datos, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>Sugerencias de programación
  
-   **Números negativos.** Dado que `UShort` es un tipo sin signo, que no puede representar un número negativo. Si usa el operador unario menos (`-`) operador en una expresión que se evalúa como tipo `UShort`, Visual Basic convierte la expresión a `Integer` primero.  
  
-   **Conformidad con CLS.** El `UShort` es de tipo de datos no forma parte de la [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código conforme a CLS no puede utilizar un componente que lo utiliza.
  
-   **Ampliación.** El `UShort` tipo de datos se amplía a `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, y `Double`. Esto significa que se puede convertir `UShort` a cualquiera de estos tipos sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.  
  
-   **Caracteres de tipo.** Anexar los caracteres de tipo literal `US` a un literal, se convierte a la `UShort` tipo de datos. `UShort` no tiene ningún carácter de tipo identificador.  
  
-   **Tipo de marco de trabajo.** El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.UInt16>  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
