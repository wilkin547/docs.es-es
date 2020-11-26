---
title: Cómo comprobar si las cadenas tienen un formato de correo electrónico válido
description: Vea un ejemplo de cómo una expresión regular comprueba que las cadenas tienen un formato de correo electrónico válido en .NET.
ms.date: 06/30/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- user input, examples
- Regex.IsMatch method
- regular expressions [.NET], examples
- examples [Visual Basic], strings
- IsValidEmail
- validation, email strings
- input, checking
- strings [.NET], examples [Visual Basic]
- email [.NET], validating
- IsMatch method
ms.assetid: 7536af08-4e86-4953-98a1-a8298623df92
ms.openlocfilehash: 88ff326e16ede6a422e9403b71905845014c4c25
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "94982497"
---
# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a>Cómo comprobar si las cadenas tienen un formato de correo electrónico válido

En el ejemplo siguiente se usa una expresión regular para comprobar que una cadena tiene un formato de correo electrónico válido.

Esta expresión regular es comparativamente más sencilla de lo que se puede usar realmente como un correo electrónico. Usar una expresión regular para validar un correo electrónico es útil para asegurarse de que la estructura del correo electrónico es correcta, pero no sustituye a la comprobación de que el correo electrónico existe realmente.

✔️ Use una expresión regular pequeña para comprobar si la estructura de un correo electrónico es válida.

✔️ Envíe un correo electrónico de prueba a la dirección proporcionada por un usuario de su aplicación.

❌ No use una expresión regular como la única manera de validar un correo electrónico.

Si intenta crear la expresión regular _perfecta_ para validar que la estructura de un correo electrónico es correcta, la expresión se vuelve tan compleja que es increíblemente difícil de depurar o mejorar. Las expresiones regulares no pueden validar la existencia de un correo electrónico, incluso aunque esté estructurado correctamente. La mejor manera de validar un correo electrónico es enviar un mensaje de correo electrónico de prueba a la dirección.

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a>Ejemplo

En el ejemplo se define un método `IsValidEmail`, que devuelve `true` si la cadena contiene una dirección de correo electrónico válida y `false` si no es válida, pero no realiza ninguna otra acción.

Para comprobar que la dirección de correo electrónico es válida, el método `IsValidEmail` llama al método <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> con el patrón de expresión regular `(@)(.+)$` para separar el nombre de dominio de la dirección de correo electrónico. El tercer parámetro es un delegado <xref:System.Text.RegularExpressions.MatchEvaluator> que representa el método que procesa y reemplaza el texto coincidente. El patrón de expresión regular se interpreta de esta manera:

| Modelo | Descripción                                                                         |
|---------|-------------------------------------------------------------------------------------|
| `(@)`   | Buscar el carácter @. Esta parte es el primer grupo de captura.                           |
| `(.+)`  | Buscar una coincidencia con una o más apariciones de cualquier carácter. Esta parte es el segundo grupo de captura. |
| `$`     | Finalizar la búsqueda al final de la cadena.                                             |

El nombre de dominio junto con el carácter @ se pasa al método `DomainMapper` , que usa la clase <xref:System.Globalization.IdnMapping> para convertir los caracteres Unicode fuera del intervalo de caracteres EE.UU. - ASCII a Punycode. El método también establece la marca `invalid` en `True` si el método <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> detecta cualquier carácter no válido en el nombre del dominio. El método devuelve el nombre de dominio Punycode precedido por el símbolo @ al método `IsValidEmail` .

> [!TIP]
> Se recomienda usar el patrón de expresión regular simple `(@)(.+)$` para normalizar el dominio y devolver un valor que indique si el resultado ha sido correcto o se ha producido un error. Sin embargo, en el ejemplo de este artículo se describe cómo usar de forma avanzada una expresión regular para validar el correo electrónico. Independientemente de cómo valide un correo electrónico, siempre debe enviar un correo electrónico de prueba a la dirección para asegurarse de que existe.

A continuación, el método `IsValidEmail` llama al método <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> para comprobar que la dirección se ajusta a un patrón de expresión regular.

El método `IsValidEmail` simplemente determina si el formato del correo electrónico es válido para una dirección de correo electrónico, no valida si el correo electrónico existe. Además, el método `IsValidEmail` no comprueba que el nombre del dominio de nivel superior sea un nombre válido enumerado en la [base de datos de la zona de la raíz de IANA](https://www.iana.org/domains/root/db), lo cual requeriría una operación de búsqueda.

:::code language="csharp" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/csharp/RegexUtilities.cs":::

:::code language="vb" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/vb/RegexUtilities.vb":::

En este ejemplo, el patrón de expresión regular `^[^@\s]+@[^@\s]+\.[^@\s]+$` se interpreta como se muestra en la tabla siguiente. La expresión regular se compila mediante la marca <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>.

| Patrón   | Descripción                                                                              |
|-----------|------------------------------------------------------------------------------------------|
| `^`       | Comenzar la búsqueda de coincidencia al principio de la cadena.                                              |
| `[^@\s]+` | Buscar una o más repeticiones de cualquier carácter que no sea el carácter @ o el espacio en blanco. |
| `@`       | Buscar el carácter @.                                                                   |
| `[^@\s]+` | Buscar una o más repeticiones de cualquier carácter que no sea el carácter @ o el espacio en blanco. |
| `\.`      | Buscar un único carácter de punto.                                                         |
| `[^@\s]+` | Buscar una o más repeticiones de cualquier carácter que no sea el carácter @ o el espacio en blanco. |
| `$`       | Finalizar la búsqueda al final de la cadena.                                                  |

> [!IMPORTANT]
> Esta expresión regular no se ha diseñado para cubrir todos los aspectos de una dirección de correo electrónico válida. Se proporciona como un ejemplo para ampliarla según sea necesario.

## <a name="see-also"></a>Vea también

- [Expresiones regulares de .NET](regular-expressions.md)
- [¿Hasta qué punto se debe llevar la validación de direcciones de correo electrónico?](https://softwareengineering.stackexchange.com/questions/78353/how-far-should-one-take-e-mail-address-validation#78363)
