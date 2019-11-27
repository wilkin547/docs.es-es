---
title: Short (Tipo de datos)
ms.date: 01/31/2018
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: 8dfdfb56de32e4b3a96729b09ccf46a6fee9a424
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343934"
---
# <a name="short-data-type-visual-basic"></a>Short (tipo de datos) (Visual Basic)

Contiene enteros de 16 bits con signo (2 bytes) que se encuentran entre-32.768 y 32.767.  
  
## <a name="remarks"></a>Comentarios  

 Utilice el tipo de datos `Short` para contener valores enteros que no requieran el ancho completo de los datos de `Integer`. En algunos casos, el Common Language Runtime puede empaquetar las variables de `Short` en estrecha colaboración y ahorrar consumo de memoria.  
  
 El valor predeterminado de `Short` es 0.  
  
## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e inicializar una variable de `Short` asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario. Si el literal entero está fuera del intervalo de `Short` (es decir, si es inferior a <xref:System.Int16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int16.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 1.034 que se representan como literales binarios, hexadecimales y decimales se convierten implícitamente de un [entero](integer-data-type.md) a `Short` valores.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> Use el prefijo `&h` o `&H` para indicar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_`, como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

A partir de Visual Basic 15,5, también puede usar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales. Por ejemplo:

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Los literales numéricos también pueden incluir el [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) `S` para indicar el tipo de datos `Short`, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a>sugerencias de programación

- **Ampliación.** El tipo de datos `Short` se amplía a `Integer`, `Long`, `Decimal`, `Single`o `Double`. Esto significa que puede convertir un tipo de datos `Short` en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Caracteres de tipo.** Al agregar el carácter de tipo literal `S` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Short`. `Short` no tiene ningún carácter de tipo de identificador.  
  
- **Tipo de marco.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Int16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Int16?displayProperty=nameWithType>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Integer (tipo de datos)](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Long (tipo de datos)](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
