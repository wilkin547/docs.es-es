---
title: Tipo de datos UShort
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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401314"
---
# <a name="ushort-data-type-visual-basic"></a>Tipo de datos UShort (Visual Basic)

Contiene enteros de 16 bits sin signo (2 bytes) que varían en valor de 0 a 65.535.  
  
## <a name="remarks"></a>Observaciones

 Utilice `UShort` el tipo de datos para `Byte`contener datos binarios demasiado grandes para .  
  
 El valor predeterminado de `UShort` es 0.  

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e `UShort` inicializar una variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (a partir de Visual Basic 2017) un literal binario. Si el literal entero está fuera del intervalo de `UShort` (es decir, si es inferior a <xref:System.UInt16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.

En el ejemplo siguiente, los enteros iguales a 65.034 que se representan `UShort` como literales decimales, hexadecimales y binarios se asignan a los valores.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> Utilice el `&h` prefijo `&H` o para denotar un `&b` `&B` literal hexadecimal, el prefijo o `&o` `&O` para denotar un literal binario, y el prefijo o para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también `_`puede usar el carácter de subrayado, , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

A partir de Visual Basic 15.5, también`_`puede usar el carácter de subrayado ( ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales. Por ejemplo:

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Los literales numéricos `US` `us` también pueden incluir `UShort` el [carácter](../../programming-guide/language-features/data-types/type-characters.md) o tipo para denotar el tipo de datos, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>sugerencias de programación
  
- **Números negativos.** Dado `UShort` que es un tipo sin signo, no puede representar un número negativo. Si utiliza el operador`-`unario menos ( ) en `UShort`una expresión que se `Integer` evalúa como tipo , Visual Basic convierte la expresión en primer lugar.  
  
- **Cumplimiento de CLS.** El `UShort` tipo de datos no forma parte de [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código compatible con CLS no puede consumir un componente que lo utilice.
  
- **Ampliación.** El `UShort` tipo de datos `Integer` `UInteger`se `Long` `ULong`amplía `Decimal` `Single`a `Double`, , , , , y . Esto significa que `UShort` puede convertir a cualquiera <xref:System.OverflowException?displayProperty=nameWithType> de estos tipos sin encontrar un error.  
  
- **Escriba Caracteres.** Anexar los caracteres `US` de tipo literal `UShort` a un literal lo fuerza al tipo de datos. `UShort`no tiene ningún carácter de tipo identificador.  
  
- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.UInt16>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
