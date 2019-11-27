---
title: UShort (Tipo de datos)
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
ms.openlocfilehash: 7cdbd5fb192fd5cc1be6260dcdcdb1f30cf3f865
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343856"
---
# <a name="ushort-data-type-visual-basic"></a>Tipo de datos UShort (Visual Basic)

Contiene enteros de 16 bits sin signo (2 bytes) con un valor comprendido entre 0 y 65.535.  
  
## <a name="remarks"></a>Comentarios

 Utilice el tipo de datos `UShort` para contener datos binarios demasiado grandes para `Byte`.  
  
 El valor predeterminado de `UShort` es 0.  

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e inicializar una variable de `UShort` asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario. Si el literal entero está fuera del intervalo de `UShort` (es decir, si es inferior a <xref:System.UInt16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 65.034 que se representan como literales binarios, hexadecimales y decimales se asignan a los valores de `UShort`.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> Use el prefijo `&h` o `&H` para indicar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_`, como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

A partir de Visual Basic 15,5, también puede usar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales. Por ejemplo:

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Los literales numéricos también pueden incluir el [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) `US` o `us` para indicar el tipo de datos `UShort`, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>sugerencias de programación
  
- **Números negativos.** Dado que `UShort` es un tipo sin signo, no puede representar un número negativo. Si usa el operador unario menos (`-`) en una expresión que se evalúa como tipo `UShort`, Visual Basic convierte la expresión en `Integer` primero.  
  
- **Conformidad con CLS.** El tipo de datos `UShort` no forma parte de la [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código conforme a CLS no puede consumir un componente que lo utiliza.
  
- **Ampliación.** El tipo de datos `UShort` se amplía a `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`y `Double`. Esto significa que puede convertir `UShort` en cualquiera de estos tipos sin encontrar un error de <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Caracteres de tipo.** Anexar los caracteres de tipo literal `US` a un literal lo convierte al tipo de datos `UShort`. `UShort` no tiene ningún carácter de tipo de identificador.  
  
- **Tipo de marco.** El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.UInt16>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
