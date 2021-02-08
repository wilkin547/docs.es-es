---
description: 'Más información sobre: tipo de datos de fecha (Visual Basic)'
title: Tipo de datos Date
ms.date: 07/20/2015
f1_keywords:
- vb.Date
helpviewer_keywords:
- Date data type
- dates [Visual Basic], Visual Basic data types
- times [Visual Basic], Date data type
- Date literals [Visual Basic]
- data values [Visual Basic]
- times [Visual Basic], Visual Basic data types
- dates [Visual Basic], Date data type
- data types [Visual Basic], assigning
- literals [Visual Basic], Date
- '# specifier for Date literals'
ms.assetid: d9edf5b0-e85e-438b-a1cf-1f321e7c831b
ms.openlocfilehash: f6ea6aa99339d13824477bba99ecd211f826a3ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99775024"
---
# <a name="date-data-type-visual-basic"></a>Date (Tipo de datos, Visual Basic)

Contiene los valores IEEE de 64 bits (8 bytes) que representan fechas comprendidas entre el 1 de enero del año 0001 hasta el 31 de diciembre del año 9999, y las horas comprendidas entre las 00:00:00 (medianoche) y las 23:59:59.9999999. Cada incremento representa 100 nanosegundos de tiempo transcurrido desde el comienzo del 1 de enero del año 1 del calendario gregoriano. El valor máximo representa 100 nanosegundos antes del comienzo del 1 de enero del año 10000.

## <a name="remarks"></a>Observaciones

Utilice el tipo de datos `Date` para contener valores de fecha, valores de hora o valores de fecha y hora.

El valor predeterminado de `Date` es 0:00:00 (medianoche) del 1 de enero de 0001.

Puede obtener la fecha y hora actuales desde la clase <xref:Microsoft.VisualBasic.DateAndTime>.

## <a name="format-requirements"></a>Requisitos de formato

Debe delimitar cualquier literal `Date` con signos de número (`# #`). Debe especificar el valor de fecha en el formato M/d/aaaa, por ejemplo `#5/31/1993#`, o aaaa-MM-dd, por ejemplo `#1993-5-31#`. Puede usar barras diagonales al especificar el año en primer lugar.  Este requisito es independiente de la configuración regional y de la configuración de formato de fecha y hora del equipo.

El motivo de esta restricción es que el significado del código nunca debe cambiar en función de la configuración regional en que se ejecuta la aplicación. Suponga que codifica un literal `Date` de `#3/4/1998#` con la intención de que signifique el 4 de marzo de 1998. En una configuración regional que use el formato mm/dd/aaaa, 3/4/1998 se compila tal como desea. Pero supongamos que implementa la aplicación en muchos países o regiones. En una configuración regional que use el formato dd/mm/aaaa, el literal incluido en el código se compilará como 3 de abril de 1998. En una configuración local que utilice el formato aaaa/mm/dd, el literal no sería válido (1998 de abril de 0003) y generaría un error de compilación.

## <a name="workarounds"></a>Soluciones

Para convertir un literal `Date` al formato de la configuración regional o a un formato personalizado, proporcione el literal a la función <xref:Microsoft.VisualBasic.Strings.Format%2A> especificando un formato de fecha predefinido o uno especificado por el usuario. En el siguiente ejemplo se muestra cómo hacerlo.

```vb
MsgBox("The formatted date is " & Format(#5/31/1993#, "dddd, d MMM yyyy"))
```

Si lo desea, también puede utilizar uno de los constructores sobrecargados de la estructura <xref:System.DateTime> para ensamblar un valor de fecha y hora. En el ejemplo siguiente se crea un valor para representar 31 de mayo de 1993 a las 12:14 del mediodía.

```vb
Dim dateInMay As New System.DateTime(1993, 5, 31, 12, 14, 0)
```

## <a name="hour-format"></a>Formato de hora

Puede especificar el valor de hora en formato de 12 horas o de 24 horas, por ejemplo, `#1:15:30 PM#` o `#13:15:30#`. Sin embargo, si no especifica los minutos o los segundos, debe especificar AM o PM.

## <a name="date-and-time-defaults"></a>Valores predeterminados de fecha y hora

Si no incluye una fecha en un literal de fecha y hora, Visual Basic establece la parte de fecha del valor en el 1 de enero de 0001. Si no incluye una hora en un literal de fecha y hora, Visual Basic establece la parte de hora del valor en el inicio del día, es decir, medianoche (0:00:00).

## <a name="type-conversions"></a>Conversiones de tipos

Si convierte un valor `Date` al tipo `String`, Visual Basic representa la fecha en función del formato corto de fecha especificado por la configuración regional en tiempo de ejecución y representa la hora de acuerdo con el formato de hora (12 o 24 horas) especificado por la configuración regional en tiempo de ejecución.

## <a name="programming-tips"></a>Sugerencias de programación

- **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para .NET Framework, por ejemplo, objetos de automatización o COM, tenga presente que los tipos de fecha y hora definidos en otros entornos no son compatibles con el tipo `Date` de Visual Basic. Al pasar un argumento de fecha y hora a esos componentes, declárelo en el código de Visual Basic como `Double` en lugar de como `Date`, y use los métodos de conversión <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> y <xref:System.DateTime.ToOADate%2A?displayProperty=nameWithType>.

- **Caracteres de tipo.** `Date` no tiene un carácter de tipo literal o un carácter de tipo de identificador. Sin embargo, el compilador trata los literales incluidos entre caracteres de signo de número (`# #`) como `Date`.

- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.DateTime?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo

Una variable o constante del tipo de datos `Date` contiene la fecha y la hora. Esto se ilustra en el siguiente ejemplo:

```vb
Dim someDateAndTime As Date = #8/13/2002 12:14 PM#
```

## <a name="see-also"></a>Vea también

- <xref:System.DateTime?displayProperty=nameWithType>
- [Tipo de datos](index.md)
- [Cadenas con formato de fecha y hora estándar](../../../standard/base-types/standard-date-and-time-format-strings.md)
- [Cadenas con formato de fecha y hora personalizado](../../../standard/base-types/custom-date-and-time-format-strings.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Resumen de las conversiones](../keywords/conversion-summary.md)
- [Uso eficiente de los tipos de datos](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
