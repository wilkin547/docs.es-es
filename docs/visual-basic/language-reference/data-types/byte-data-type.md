---
title: Tipo de datos Byte
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401356"
---
# <a name="byte-data-type-visual-basic"></a>Tipo de datos byte (Visual Basic)

Contiene enteros sin signo de 8 bits (1 byte) que oscilan en valor de 0 a 255.

## <a name="remarks"></a>Observaciones

Utilice `Byte` el tipo de datos para contener datos binarios.  
  
El valor predeterminado de `Byte` es 0.

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e `Byte` inicializar una variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (a partir de Visual Basic 2017) un literal binario. Si el literal entero está `Byte` fuera del intervalo de a <xref:System.Byte.MinValue?displayProperty=nameWithType> (es <xref:System.Byte.MaxValue?displayProperty=nameWithType>decir, si es menor o mayor que ), se produce un error de compilación.

En el ejemplo siguiente, los enteros iguales a 201 que se representan como [Integer](integer-data-type.md) literales `byte` decimales, hexadecimales y binarios se convierten implícitamente de Entero a valores.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Utilice el `&h` prefijo `&H` o para denotar un `&b` `&B` literal hexadecimal, el prefijo o `&o` `&O` para denotar un literal binario, y el prefijo o para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también `_`puede usar el carácter de subrayado, , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

A partir de Visual Basic 15.5, también`_`puede usar el carácter de subrayado ( ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales. Por ejemplo:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>sugerencias de programación

- **Números negativos.** Dado `Byte` que es un tipo sin signo, no puede representar un número negativo. Si utiliza el operador`-`unario menos ( ) en `Byte`una expresión que se `Short` evalúa como tipo , Visual Basic convierte la expresión en primer lugar.
  
- **Conversiones de formato.** Cuando Visual Basic lee o escribe archivos, o cuando llama a archivos DLL, métodos y propiedades, puede convertir automáticamente entre formatos de datos. Los datos `Byte` binarios almacenados en variables y matrices se conservan durante dichas conversiones de formato. No debe utilizar `String` una variable para los datos binarios, ya que su contenido puede dañarse durante la conversión entre formatos ANSI y Unicode.

- **Ampliación.** El `Byte` tipo de datos `Short` `UShort`se `Integer` `UInteger`amplía `Long` `ULong`a `Decimal` `Single`, `Double`, , , , , , o . Esto significa que `Byte` puede convertir a cualquiera <xref:System.OverflowException?displayProperty=nameWithType> de estos tipos sin encontrar un error.
  
- **Escriba Caracteres.** `Byte`no tiene ningún carácter de tipo literal o carácter de tipo identificador.

- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Byte?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo

 En el ejemplo `b` siguiente, es una `Byte` variable. Las instrucciones muestran el rango de la variable y la aplicación de operadores de desplazamiento de bits a ella.

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>Consulte también

- <xref:System.Byte?displayProperty=nameWithType>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
