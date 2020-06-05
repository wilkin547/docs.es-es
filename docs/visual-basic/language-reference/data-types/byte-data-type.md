---
title: Tipo de datos Byte
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 97acd1bc2ff29bac6588216b9ee4a4f187078815
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374322"
---
# <a name="byte-data-type-visual-basic"></a>Byte (tipo de datos) (Visual Basic)

Contiene enteros de 8 bits sin signo (1 byte) que oscilan entre 0 y 255.

## <a name="remarks"></a>Observaciones

Utilice el `Byte` tipo de datos para contener datos binarios.  
  
El valor predeterminado de `Byte` es 0.

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e inicializar una `Byte` variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario. Si el literal entero está fuera del intervalo de `Byte` (es decir, si es menor que <xref:System.Byte.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Byte.MaxValue?displayProperty=nameWithType> ), se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 201 que se representan como literales binarios, hexadecimales y decimales se convierten implícitamente de [enteros](integer-data-type.md) a `byte` valores.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario, y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_` , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

A partir de Visual Basic 15,5, también puede usar el carácter de subrayado ( `_` ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales. Por ejemplo:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>sugerencias de programación

- **Números negativos.** Dado `Byte` que es un tipo sin signo, no puede representar un número negativo. Si usa el operador unario menos ( `-` ) en una expresión que se evalúa como tipo `Byte` , Visual Basic convierte primero la expresión en `Short` .
  
- **Conversiones de formato.** Cuando Visual Basic lee o escribe archivos, o cuando llama a archivos dll, métodos y propiedades, puede convertir automáticamente entre formatos de datos. Los datos binarios almacenados en `Byte` variables y matrices se conservan durante las conversiones de formato. No debe utilizar una `String` variable para los datos binarios, porque su contenido se puede dañar durante la conversión entre los formatos ANSI y Unicode.

- **Ampliación.** El `Byte` tipo de datos se amplía a `Short` , `UShort` , `Integer` , `UInteger` ,,, `Long` `ULong` `Decimal` , `Single` o `Double` . Esto significa que puede convertir `Byte` en cualquiera de estos tipos sin que se produzca un <xref:System.OverflowException?displayProperty=nameWithType> error.
  
- **Caracteres de tipo.** `Byte`no tiene un carácter de tipo literal o un carácter de tipo de identificador.

- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Byte?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente, `b` es una `Byte` variable. Las instrucciones muestran el intervalo de la variable y la aplicación de los operadores de desplazamiento de bits a ella.

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>Consulte también

- <xref:System.Byte?displayProperty=nameWithType>
- [Tipos de datos](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Resumen de las conversiones](../keywords/conversion-summary.md)
- [Uso eficiente de los tipos de datos](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
