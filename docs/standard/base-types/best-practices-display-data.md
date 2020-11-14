---
title: Procedimientos recomendados para mostrar y conservar datos con formato en .NET
description: Obtenga información sobre cómo mostrar y conservar datos numéricos y de fecha de manera eficaz en las aplicaciones .NET.
ms.date: 05/01/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.openlocfilehash: 83a491f6c843225c6242a343fe4132c2ce7caa74
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "93403495"
---
# <a name="best-practices-for-displaying-and-persisting-formatted-data"></a>Procedimientos recomendados para mostrar y conservar datos con formato

En este artículo se examina cómo se usan para la presentación y el almacenamiento los datos con formato, como los datos numéricos y los datos de fecha y hora.

Cuando desarrolle con .NET, use el formato dependiente de la referencia cultural para mostrar datos que no son de cadena, como números y fechas, en una interfaz de usuario. Use el formato con la [referencia cultural invariable](xref:System.Globalization.CultureInfo.InvariantCulture) para conservar datos que no son de cadena en forma de cadena. No use el formato dependiente de la referencia cultural para conservar datos numéricos o datos de fecha y hora en formato de cadena.

## <a name="displaying-formatted-data"></a>Visualización de datos con formato

Cuando muestre a los usuarios datos que no sean de cadena, como números, y fechas y horas, asígneles formato mediante la configuración de la referencia cultural del usuario. De forma predeterminada, los siguientes elementos usan la referencia cultural del subproceso actual al dar formato a las operaciones:

- Cadenas interpoladas compatibles con los compiladores [C#](../../csharp/language-reference/tokens/interpolated.md) y [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md).
- Operaciones de concatenación de cadenas que usan los operadores de concatenación [C#](../../csharp/language-reference/operators/addition-operator.md#string-concatenation) o [Visual Basic](../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md), o que llaman al método <xref:System.String.Concat%2A?displayProperty=nameWithType> directamente.
- El método <xref:System.String.Format%2A?displayProperty=nameWithType> .
- Métodos `ToString` de los tipos numéricos y tipos de fecha y hora.

Para especificar explícitamente que se debe dar formato a una cadena mediante las convenciones de una referencia cultural nombrada o la [referencia cultural invariable](xref:System.Globalization.CultureInfo.InvariantCulture), se puede hacer lo siguiente:

- Cuando se usen los métodos <xref:System.String.Format%2A?displayProperty=nameWithType> y `ToString`, llame a una sobrecarga que tenga un parámetro `provider`, como <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> o <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType>, y pásela a la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>, a una instancia <xref:System.Globalization.CultureInfo> que represente la referencia cultural que se quiera o a la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.

- Para la concatenación de cadenas, no permita que el compilador realice ninguna de las conversiones implícitas. En su lugar, realice una conversión explícita mediante una llamada a una sobrecarga `ToString` que tenga un parámetro `provider`. Por ejemplo, el compilador utiliza implícitamente la referencia cultural actual cuando convierte un valor <xref:System.Double> en una cadena en el código siguiente:

  [!code-csharp[Implicit String Conversion](./snippets/best-practices-strings/csharp/tostring/Program.cs#1)]
  [!code-vb[Implicit String Conversion](./snippets/best-practices-strings/vb/tostring/Program.vb#1)]

  En su lugar, se puede especificar explícitamente la referencia cultural cuyas convenciones de formato se usan en la conversión mediante una llamada al método <xref:System.Double.ToString(System.IFormatProvider)?displayProperty=nameWithType>, tal como hace el código siguiente:

  [!code-csharp[Explicit String Conversion](./snippets/best-practices-strings/csharp/tostring/Program.cs#2)]
  [!code-vb[Implicit String Conversion](./snippets/best-practices-strings/vb/tostring/Program.vb#2)]

- Para la interpolación de cadenas, en lugar de asignar una cadena interpolada a una instancia <xref:System.String>, asígnela a un elemento <xref:System.FormattableString>. Después, se puede llamar al método <xref:System.FormattableString.ToString?displayProperty=nameWithType> para generar una cadena de resultado que refleje las convenciones de la referencia cultural actual, o bien puede llamar al método <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> para generar una cadena de resultado que refleje las convenciones de la referencia cultural especificada. También se puede pasar la cadena que admite formato al método estático <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> con el fin de generar una cadena de resultado que refleje las convenciones de la referencia cultural invariable. En el ejemplo siguiente se muestra este enfoque. (La salida del ejemplo refleja una referencia cultural actual de en-US).

  [!code-csharp[String interpolation](./snippets/best-practices-strings/csharp/formattable/Program.cs)]
  [!code-vb[String interpolation](./snippets/best-practices-strings/vb/formattable/Program.vb)]

## <a name="persisting-formatted-data"></a>Conservación de datos con formato

Puede conservar datos que no son de cadena como datos binarios o como datos con formato. Si decide guardarlos como datos con formato, debe llamar a una sobrecarga del método de formato que incluya un parámetro `provider` y pasarle la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> . La referencia cultural de todos los idiomas proporciona un formato coherente para los datos con formato que es independiente de la referencia cultural y del equipo. En cambio, si se conservan datos a los que se aplica formato con referencias culturales distintas de la referencia cultural de todos los idiomas, se presentan varias limitaciones:

- Es probable que los datos no puedan usarse si se recuperan en un sistema que tiene una referencia cultural distinta, o si el usuario del sistema actual cambia la referencia cultural actual e intenta recuperar los datos.
- Las propiedades de una referencia cultural en un equipo específico pueden diferir de los valores estándar. En cualquier momento, un usuario puede personalizar la configuración de visualización que depende de la cultural. Debido a esto, es posible que los datos con formato que se guardan en un sistema no sean legibles después de que el usuario personalice la configuración de la referencia cultural. Es posible que la portabilidad de los datos con formato entre equipos sea incluso más limitada.
- Las normas internacionales, regionales o nacionales que rigen el formato de los números o las fechas y horas cambian con el tiempo, y estos cambios se incorporan en las actualizaciones de los sistemas operativos Windows. Cuando cambian las convenciones de formato, los datos a los que se aplicó formato usando las convenciones anteriores pueden llegar a ser ilegibles.

En el ejemplo siguiente se muestra la portabilidad limitada que se deriva de usar el formato dependiente de la referencia cultural para conservar los datos. En el ejemplo se guarda una matriz de valores de fecha y hora en un archivo. Se les da formato con las convenciones de la referencia cultural Inglés (Estados Unidos). Después de que la aplicación cambie la referencia cultural del subproceso actual a Francés (Suiza), intenta leer los valores guardados usando las convenciones de formato de la referencia cultural actual. El intento de leer dos de los elementos de datos genera una excepción <xref:System.FormatException> y la matriz de fechas ahora contiene dos elementos incorrectos que iguales a <xref:System.DateTime.MinValue>.

[!code-csharp[Conceptual.Strings.BestPractices#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/persistence.cs#21)]
[!code-vb[Conceptual.Strings.BestPractices#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/persistence.vb#21)]

Pero si reemplaza la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> por <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> en las llamadas a <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> y a <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, los datos persistentes de fecha y hora se restauran correctamente, como se muestra en la salida siguiente:

```console
06.05.1758 21:26
05.05.1818 07:19
22.04.1870 23:54
08.09.1890 06:47
18.02.1905 15:12
```
