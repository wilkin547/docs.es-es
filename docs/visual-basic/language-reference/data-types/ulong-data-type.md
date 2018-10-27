---
title: ULong (Tipo de datos, Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
ms.openlocfilehash: 13dec9f298655a4bfe6672e2dbba7c7262379cc4
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50033537"
---
# <a name="ulong-data-type-visual-basic"></a>Tipo de datos de ULong (Visual Basic)

Contiene enteros de (8 bytes) de 64 bits sin signo cuyo valor oscila de 0 a 18.446.744.073.709.551.615 (1,84 veces más de 10 ^ 19).  
  
## <a name="remarks"></a>Comentarios

Use la `ULong` tipo de datos para contener datos binarios demasiado grandes para `UInteger`, o valores enteros sin signo lo más grande posible.  
  
El valor predeterminado de `ULong` es 0.

## <a name="literal-assignments"></a>Asignaciones de literales

Puede declarar e inicializar un `ULong` variable mediante la asignación de un literal decimal, un literal hexadecimal, un literal octal, o (a partir de 2017 Visual Basic) un literal binario. Si el literal entero está fuera del intervalo de `ULong` (es decir, si es inferior a <xref:System.UInt64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 7 934 076 125 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `ULong`.
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como en el ejemplo siguiente se muestra.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

A partir de Visual Basic 15.5, también puede usar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales. Por ejemplo:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

También pueden incluir literales numéricos el `UL` o `ul` [carácter de tipo](../../programming-guide\language-features\data-types/type-characters.md) para denotar el `ULong` tipo de datos, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>Sugerencias de programación
  
-   **Números negativos.** Dado que `ULong` es un tipo sin signo, que no puede representar un número negativo. Si usa el operador unario menos (`-`) operador en una expresión que se evalúa como tipo `ULong`, Visual Basic convierte la expresión a `Decimal` primero.  
  
-   **Conformidad con CLS.** El `ULong` es de tipo de datos no forma parte de la [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código conforme a CLS no puede utilizar un componente que lo utiliza.  
  
-   **Consideraciones de interoperabilidad.** Si interactúa con componentes no escritos para .NET Framework, por ejemplo objetos de automatización o COM, tenga en cuenta que los tipos, como `ulong` puede tener un ancho de datos diferente (32 bits) en otros entornos. Si se pasa un argumento de 32 bits a esos componentes, declárelo como `UInteger` en lugar de `ULong` en el código administrado de Visual Basic.  
  
     Además, la automatización no admite enteros de 64 bits en Windows 95, Windows 98, Windows Millennium Edition o Windows 2000. No se puede pasar de Visual Basic `ULong` argumento a un componente de automatización en estas plataformas.  
  
-   **Ampliación.** El `ULong` tipo de datos se amplía a `Decimal`, `Single`, y `Double`. Esto significa que se puede convertir `ULong` a cualquiera de estos tipos sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.  
  
-   **Caracteres de tipo.** Anexar los caracteres de tipo literal `UL` a un literal, se convierte a la `ULong` tipo de datos. `ULong` no tiene ningún carácter de tipo identificador.
  
-   **Tipo de marco de trabajo.** El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt64?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

 <xref:System.UInt64>  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
