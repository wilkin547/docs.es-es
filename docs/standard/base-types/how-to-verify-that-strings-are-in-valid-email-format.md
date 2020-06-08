---
title: Cómo comprobar si las cadenas tienen un formato de correo electrónico válido
ms.date: 12/10/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- user input, examples
- Regex.IsMatch method
- regular expressions [.NET Framework], examples
- examples [Visual Basic], strings
- IsValidEmail
- validation, email strings
- input, checking
- strings [.NET Framework], examples [Visual Basic]
- email [.NET Framework], validating
- IsMatch method
ms.assetid: 7536af08-4e86-4953-98a1-a8298623df92
ms.openlocfilehash: 360ed985575358dd9603a55fc2d5d6c297621ec8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290427"
---
# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a>Cómo comprobar si las cadenas tienen un formato de correo electrónico válido

En el ejemplo siguiente se usa una expresión regular para comprobar que una cadena tiene un formato de correo electrónico válido.

## <a name="example"></a>Ejemplo

En el ejemplo se define un método `IsValidEmail` , que devuelve `true` si la cadena contiene una dirección de correo electrónico válida y `false` si no es válida, pero no realiza ninguna otra acción.

Para comprobar que la dirección de correo electrónico es válida, el método `IsValidEmail` llama al método <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> con el patrón de expresión regular `(@)(.+)$` para separar el nombre de dominio de la dirección de correo electrónico. El tercer parámetro es un delegado <xref:System.Text.RegularExpressions.MatchEvaluator> que representa el método que procesa y reemplaza el texto coincidente. El patrón de expresión regular se interpreta de esta manera:

|Modelo|Descripción|
|-------------|-----------------|
|`(@)`|Buscar el carácter @. Este es el primer grupo de captura.|
|`(.+)`|Buscar una coincidencia con una o más apariciones de cualquier carácter. Este es el segundo grupo de captura.|
|`$`|Finalizar la búsqueda al final de la cadena.|

El nombre de dominio junto con el carácter @ se pasa al método `DomainMapper` , que usa la clase <xref:System.Globalization.IdnMapping> para convertir los caracteres Unicode fuera del intervalo de caracteres EE.UU. - ASCII a Punycode. El método también establece la marca `invalid` en `True` si el método <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> detecta cualquier carácter no válido en el nombre del dominio. El método devuelve el nombre de dominio Punycode precedido por el símbolo @ al método `IsValidEmail` .

A continuación, el método `IsValidEmail` llama al método <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> para comprobar que la dirección se ajusta a un patrón de expresión regular.

Tenga en cuenta que el método `IsValidEmail` no realiza la autenticación para validar la dirección de correo electrónico. Se limita a determinar si su formato es válido para una dirección de correo electrónico. Asimismo, el método `IsValidEmail` no comprueba que el nombre del dominio de nivel superior sea un nombre válido enumerado en la [base de datos de la zona de la raíz IANA](https://www.iana.org/domains/root/db), lo cual requeriría una operación de búsqueda. En su lugar, la expresión regular comprueba simplemente que el nombre de dominio de nivel superior conste de entre dos y veinticuatro caracteres ASCII alfanuméricos, que los caracteres primero y último sean alfanuméricos y que el resto de caracteres sean alfanuméricos o un guión (-).

[!code-csharp[RegularExpressions.Examples.Email#7](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Email/cs/example4.cs#7)]
[!code-vb[RegularExpressions.Examples.Email#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Email/vb/example4.vb#7)]

En este ejemplo, el patrón de expresión regular ``^(?(")(".+?(?<!\\)"@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w])*)(?<=[0-9a-z])@))(?(\[)(\[(\d{1,3}\.){3}\d{1,3}\])|(([0-9a-z][-0-9a-z]*[0-9a-z]*\.)+[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))$`` se interpreta como se muestra en la leyenda siguiente. La expresión regular se compila mediante la marca <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>.

Patrón `^`: Comenzar la búsqueda de coincidencia al principio de la cadena.

Patrón `(?(")`: Determinar si el primer carácter es una comilla. `(?(")` es el principio de una construcción de alternancia.

Patrón `(?(")(".+?(?<!\\)"@)`: Si el primer carácter es un signo de comillas, buscar unas comillas iniciales seguidas de al menos un carácter cualquiera, seguido a su vez de unas comillas finales. Las comillas finales no pueden ir precedidas de un carácter de barra diagonal inversa (\\). `(?<!` es el principio de una aserción de búsqueda anticipada negativa de ancho cero. La cadena debe concluir con una arroba (@).

Patrón `|(([0-9a-z]`: Si el primer carácter no es un signo de comillas, buscar cualquier carácter alfabético de la a a la z o de la A a la Z (la comparación distingue entre mayúsculas y minúsculas) o cualquier carácter numérico del 0 al 9.

Patrón `(\.(?!\.))`: Si el carácter siguiente es un punto, determinar que coincide. Si no lo es, buscar más adelante en el siguiente carácter y probar si coincide. `(?!\.)` es una aserción de búsqueda anticipada negativa de ancho igual a cero que evita que aparezcan dos puntos consecutivos en la parte local de una dirección de correo electrónico.

Patrón ``|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w]``: Si el carácter siguiente no es un punto, busque la coincidencia de cualquier carácter de palabra o uno de los caracteres siguientes: -!#$%&'\*+/=?^\`{}|~

Patrón ``((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w])*``: Buscar el modelo de alternancia (un punto seguido de algo que no sea un punto, o uno de varios caracteres) cero o más veces.

Patrón `@`: Buscar el carácter @.

Patrón `(?<=[0-9a-z])`: Continuar buscando si el carácter que precede al carácter @ es uno de la A a la Z, de la a a la z o del 0 al 9. Este patrón define una aserción de búsqueda retrasada (lookbehind) positiva de ancho cero.

Patrón `(?(\[)`: Comprobar si el carácter que va detrás de @ es un corchete de apertura.

Patrón `(\[(\d{1,3}\.){3}\d{1,3}\])`: Si lo es, buscar el corchete de apertura, seguido por una dirección IP (cuatro grupos de uno a tres dígitos, separados por puntos) y por un corchete de cierre.

Patrón `|(([0-9a-z][-0-9a-z]*[0-9a-z]*\.)+`: Si el carácter que va detrás de @ no es un corchete de apertura, buscar un carácter alfanumérico con un valor de la A a la Z, de la a a la z o del 0 al 9, seguido de cero o más apariciones de un guión, seguido de cero o de un carácter alfanumérico con un valor de la A a la Z, de la a a la z o del 0 al 9, seguido de un punto. Este patrón se puede repetir una o más veces y debe ir seguido del nombre de dominio de nivel superior.

Patrón `[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))`: El nombre de dominio de nivel superior debe empezar y finalizar por un carácter alfanumérico (a-z, A-Z y 0-9). También puede incluir de cero a 22 caracteres ASCII que sean alfanuméricos o guiones.

Patrón `$`: Finalizar la búsqueda al final de la cadena.

## <a name="compile-the-code"></a>Compilar el código

Los métodos `IsValidEmail` y `DomainMapper` pueden estar incluidos en una biblioteca de métodos de la utilidad de expresiones regulares o pueden incluirse como métodos estáticos o de instancia privados en la clase de aplicación.

También puede usar el método <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> para incluir esta expresión regular en una biblioteca de expresiones regulares.

Si se utilizan en una biblioteca de expresiones regulares, puede llamarlos utilizando código como el siguiente:

[!code-csharp[RegularExpressions.Examples.Email#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Email/cs/example4.cs#8)]
[!code-vb[RegularExpressions.Examples.Email#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Email/vb/example4.vb#8)]

## <a name="see-also"></a>Vea también

- [Expresiones regulares de .NET Framework](regular-expressions.md)
