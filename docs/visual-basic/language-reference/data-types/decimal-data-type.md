---
title: Tipo de datos Decimal
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: d4d868ba7c05cf3c2d538de1217231df91d4f43d
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243328"
---
# <a name="decimal-data-type-visual-basic"></a>Decimal (Tipo de datos, Visual Basic)

Contiene valores de 128 bits (16 bytes) firmados que representan números enteros de 96 bits (12 bytes) escalados por una potencia variable de 10. El factor de escala especifica el número de dígitos a la derecha del punto decimal; oscila entre 0 y 28. Con una escala de 0 (sin decimales), el mayor valor posible es +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28). Con 28 decimales, el valor más grande es +/-7.9228162514264337593543950335, y el valor distinto de cero más pequeño es +/-00000000000000000000000000000001 (+/-1E-28).

## <a name="remarks"></a>Observaciones

El `Decimal` tipo de datos proporciona el mayor número de dígitos significativos para un número. Soporta hasta 29 dígitos significativos y puede representar valores superiores a 7.9228 x 10-28. Es particularmente adecuado para cálculos, como financieros, que requieren un gran número de dígitos, pero no pueden tolerar errores de redondeo.

El valor predeterminado de `Decimal` es 0.

## <a name="programming-tips"></a>Sugerencias de programación

- **Precisión.** `Decimal`no es un tipo de datos de punto flotante. La `Decimal` estructura contiene un valor entero binario, junto con un bit de signo y un factor de escala entero que especifica qué parte del valor es una fracción decimal. Debido a `Decimal` esto, los números tienen una representación`Single` más `Double`precisa en la memoria que los tipos de punto flotante ( y ).

- **Rendimiento.** El `Decimal` tipo de datos es el más lento de todos los tipos numéricos. Debe sopesar la importancia de la precisión frente al rendimiento antes de elegir un tipo de datos.

- **Ampliación.** El `Decimal` tipo de datos `Single` `Double`se amplía a o . Esto significa que `Decimal` puede convertir a cualquiera <xref:System.OverflowException?displayProperty=nameWithType> de estos tipos sin encontrar un error.

- **Trailing Zeros.** Visual Basic no almacena ceros `Decimal` finales en un literal. Sin `Decimal` embargo, una variable conserva los ceros finales adquiridos computacionalmente. Esto se ilustra en el siguiente ejemplo.

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  La salida `MsgBox` del ejemplo anterior es la siguiente:

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- **Escriba Caracteres.** Al agregar el carácter de tipo literal `D` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Decimal`. Si se agrega el carácter de tipo identificador `@` a cualquier identificador, se convierte forzosamente al tipo `Decimal`.

- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Decimal?displayProperty=nameWithType>.

## <a name="range"></a>Intervalo

 Es posible que `D` deba utilizar el carácter `Decimal` de tipo para asignar un valor grande a una variable o constante. Este requisito se debe a que `Long` el compilador interpreta un literal como a menos que un carácter de tipo literal siga el literal, como se muestra en el ejemplo siguiente.

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

La declaración para `bigDec1` no produce un desbordamiento porque el valor que `Long`se le asigna se encuentra dentro del intervalo para . El `Long` valor se puede `Decimal` asignar a la variable.

La declaración para `bigDec2` genera un error de desbordamiento porque el `Long`valor que se le asigna es demasiado grande para . Dado que el literal numérico no se `Long`puede interpretar primero como `Decimal` un , no se puede asignar a la variable.

Para `bigDec3`, el `D` carácter de tipo literal resuelve el problema `Decimal` forzando `Long`al compilador a interpretar el literal como un archivo .

## <a name="see-also"></a>Consulte también

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Tipo de datos Single](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Tipo de datos Double](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de las conversiones](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso eficiente de los tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
