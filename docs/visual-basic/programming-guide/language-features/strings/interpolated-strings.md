---
title: Cadenas interpoladas
ms.date: 10/31/2017
ms.openlocfilehash: c427b48ce58a59ff3878f24f1989db6ac8c8239a
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805283"
---
# <a name="interpolated-strings-visual-basic-reference"></a>Cadenas interpoladas (referencia de Visual Basic)

Se utiliza para construir cadenas.  Una cadena interpolada es similar a una cadena de plantilla que contiene *expresiones interpoladas*.  Una cadena interpolada devuelve una cadena que reemplaza a las expresiones interpoladas que contiene por sus representaciones de cadena. Esta característica está disponible en Visual Basic 14 y versiones posteriores.

Los argumentos de una cadena interpolada son más fáciles de entender que una [cadena de formato compuesto](../../../../standard/base-types/composite-formatting.md#composite-format-string).  Por ejemplo, la cadena interpolada

```vb
Console.WriteLine($"Name = {name}, hours = {hours:hh}")
```

contiene dos expresiones interpoladas, "{name}" y "{hours:hh}". La cadena de formato compuesto equivalente es esta:

```vb
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours)
```

La estructura de una cadena interpolada es la siguiente:

```vb
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."
```

Donde:

- *field-width* es un entero con signo que indica el número de caracteres del campo. Si es positivo, el campo está alineado a la derecha. Si es negativo, está alineado a la izquierda.

- *format-string* es una cadena de formato adecuada para el tipo de objeto al que se da formato. Por ejemplo, para un <xref:System.DateTime> valor, podría ser una [cadena con formato de fecha y hora estándar](../../../../standard/base-types/standard-date-and-time-format-strings.md) , como "d" o "d".

> [!IMPORTANT]
> No puede haber ningún espacio en blanco entre el carácter `$` y el carácter `"` que inicia la cadena. Si lo hace, se producirá un error del compilador.

Puede utilizar una cadena interpolada en cualquier lugar que pueda utilizar un literal de cadena.  La cadena interpolada se evalúa cada vez que se ejecuta el código con la cadena interpolada. Esto le permite separar la definición y la evaluación de una cadena interpolada.

Para incluir una llave ("{" o "}") en una cadena interpolada, use dos llaves, "{{" o "}}".  Consulte la sección Conversiones implícitas para obtener más detalles.

Si la cadena interpolada contiene otros caracteres con un significado especial en una cadena interpolada, como comillas dobles ("), dos puntos (:) o coma (,), deben incluirse entre caracteres de escape si aparecen en texto literal, o bien deben incluirse en una expresión delimitada por paréntesis si son elementos del lenguaje incluidos en una expresión interpolada. En el siguiente ejemplo se da de escape las comillas para incluirlas en la cadena de resultado:

[!code-vb[interpolated-strings](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings4.vb)]

## <a name="implicit-conversions"></a>Conversiones implícitas

Hay tres conversiones de tipo implícito de una cadena interpolada:

1. Conversión de una cadena interpolada a <xref:System.String>. En el ejemplo siguiente se devuelve una cadena cuyas expresiones de cadena interpolada se han reemplazado por las representaciones de cadena. Por ejemplo:

   [!code-vb[interpolated-strings1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings1.vb)]

   Este es el resultado final de una interpretación de cadena. Todas las apariciones de llaves dobles ("{{" y "}}") se convierten en una única llave.

2. Conversión de una cadena interpolada a una variable <xref:System.IFormattable> que permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia <xref:System.IFormattable>. Esto resulta útil para incluir elementos como los formatos numéricos y de fecha correctos para cada referencia cultural.  Todas las apariciones de llaves dobles ("{{" y "}}") permanecen como llaves dobles hasta que dé formato a la cadena mediante una llamada implícita o explícita al método <xref:System.Object.ToString>.  Todas las expresiones de interpolación contenidas se convierten en {0} , {1} , etc.

   En el ejemplo siguiente se usa la reflexión para mostrar los miembros y los valores de propiedad y campo de una variable <xref:System.IFormattable> que se crea a partir de una cadena interpolada. También pasa la variable <xref:System.IFormattable> al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>.

   [!code-vb[interpolated-strings2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings2.vb)]

   Tenga en cuenta que la cadena interpolada solo se puede inspeccionar mediante reflexión. Si se pasa a un método de formato de cadena, como <xref:System.Console.WriteLine(System.String)>, sus elementos de formato se resuelven y se devuelve la cadena de resultado.

3. Conversión de una cadena interpolada a una <xref:System.FormattableString> variable que representa una cadena de formato compuesto. El hecho de inspeccionar la cadena de formato compuesto y la manera en que se presenta como cadena de resultado podría ayudarle a protegerse frente a un ataque por inyección si estuviese compilando una consulta. <xref:System.FormattableString>También incluye:

      - Una sobrecarga de <xref:System.FormattableString.ToString> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.CurrentCulture>.

      - Un <xref:System.FormattableString.Invariant%2A> método que genera una cadena para <xref:System.Globalization.CultureInfo.InvariantCulture> .

      - Un método <xref:System.FormattableString.ToString(System.IFormatProvider)> que genera una cadena de resultado para una referencia cultural especificada.

    Todas las apariciones de llaves dobles ("{{" y "}}") permanecen como llaves dobles hasta que dé formato.  Todas las expresiones de interpolación contenidas se convierten en {0} , {1} , etc.

   [!code-vb[interpolated-strings3](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings3.vb)]

## <a name="see-also"></a>Vea también

- <xref:System.IFormattable?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- [Referencia del lenguaje Visual Basic](index.md)
