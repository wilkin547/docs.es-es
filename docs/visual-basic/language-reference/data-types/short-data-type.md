---
title: Short (Tipo de datos, Visual Basic)
ms.date: 01/31/2018
author: rpetrusha
ms.author: ronpet
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
ms.openlocfilehash: ef99743828d8d80844486b651178622ff45fd554
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590717"
---
# <a name="short-data-type-visual-basic"></a>Tipo de datos short (Visual Basic)
Contiene enteros con signo 16 bits (2 bytes) que intervalo entre -32.768 y 32.767.  
  
## <a name="remarks"></a>Comentarios  
 Use la `Short` tipo de datos para contener valores enteros que no requieren el ancho completo de datos de `Integer`. En algunos casos, common language runtime puede empaquetar su `Short` variables estrecha colaboración y ahorre consumo de memoria.  
  
 El valor predeterminado de `Short` es 0.  
  
## <a name="literal-assignments"></a>Asignaciones de literales

Puede declarar e inicializar un `Short` variable asignarle un decimal literal, un literal hexadecimal, un literal octal, o (a partir de Visual Basic de 2017) un literal binario. Si el literal entero está fuera del intervalo de `Short` (es decir, si es inferior a <xref:System.Int16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int16.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.

En el siguiente ejemplo, enteros es igual a 1,034 que se representan como decimal, hexadecimal, y literales binarios se convierten implícitamente desde [entero](integer-data-type.md) a `Short` valores.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic de 2017, también puede utilizar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como en el ejemplo siguiente se muestra.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

A partir de Visual Basic 15,5, también puede utilizar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, octales o binarios. Por ejemplo:

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

También pueden incluir literales numéricos el `S` [escriba carácter](../../programming-guide\language-features\data-types/type-characters.md) para denotar el `Short` tipo de datos, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a>Sugerencias de programación

-   **De ampliación.** El `Short` tipo de datos se amplía a `Integer`, `Long`, `Decimal`, `Single`, o `Double`. Esto significa que puede convertir un tipo de datos `Short` en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=nameWithType>.  
  
-   **Caracteres de tipo.** Al agregar el carácter de tipo literal `S` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Short`. `Short` no tiene ningún carácter de tipo identificador.  
  
-   **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Int16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

 <xref:System.Int16?displayProperty=nameWithType>  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Integer (tipo de datos)](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Long (tipo de datos)](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
