---
title: Byte (Tipo de datos)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344077"
---
# <a name="byte-data-type-visual-basic"></a>Byte (tipo de datos) (Visual Basic)

Contiene enteros de 8 bits sin signo (1 byte) que oscilan entre 0 y 255.

## <a name="remarks"></a>Comentarios

Utilice el tipo de datos `Byte` para contener datos binarios.  
  
El valor predeterminado de `Byte` es 0.

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e inicializar una variable de `Byte` asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario. Si el literal entero está fuera del intervalo de una `Byte` (es decir, si es menor que <xref:System.Byte.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Byte.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 201 que se representan como literales binarios, hexadecimales y decimales se convierten implícitamente de un [entero](integer-data-type.md) a `byte` valores.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Use el prefijo `&h` o `&H` para indicar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_`, como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

A partir de Visual Basic 15,5, también puede usar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales. Por ejemplo:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>sugerencias de programación

- **Números negativos.** Dado que `Byte` es un tipo sin signo, no puede representar un número negativo. Si usa el operador unario menos (`-`) en una expresión que se evalúa como tipo `Byte`, Visual Basic convierte la expresión en `Short` primero.
  
- **Conversiones de formato.** Cuando Visual Basic lee o escribe archivos, o cuando llama a archivos dll, métodos y propiedades, puede convertir automáticamente entre formatos de datos. Los datos binarios almacenados en `Byte` variables y matrices se conservan durante las conversiones de formato. No debe utilizar una variable `String` para los datos binarios, porque su contenido se puede dañar durante la conversión entre los formatos ANSI y Unicode.

- **Ampliación.** El tipo de datos `Byte` se amplía a `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`o `Double`. Esto significa que puede convertir `Byte` en cualquiera de estos tipos sin encontrar un error de <xref:System.OverflowException?displayProperty=nameWithType>.
  
- **Caracteres de tipo.** `Byte` no tiene un carácter de tipo literal o un carácter de tipo de identificador.

- **Tipo de marco.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Byte?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente, `b` es una variable de `Byte`. Las instrucciones muestran el intervalo de la variable y la aplicación de los operadores de desplazamiento de bits a ella.

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>Vea también

- <xref:System.Byte?displayProperty=nameWithType>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
