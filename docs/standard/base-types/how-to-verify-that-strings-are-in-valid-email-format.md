---
title: Cómo comprobar si las cadenas tienen un formato de correo electrónico válido
description: Vea un ejemplo de cómo una expresión regular comprueba que las cadenas tienen un formato de correo electrónico válido en .NET.
ms.date: 06/30/2020
ms.technology: dotnet-standard
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
ms.openlocfilehash: 07b8e31e4a0203b87492eb01ab686a1c56f5565d
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889080"
---
# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a><span data-ttu-id="04ed8-103">Cómo comprobar si las cadenas tienen un formato de correo electrónico válido</span><span class="sxs-lookup"><span data-stu-id="04ed8-103">How to verify that strings are in valid email format</span></span>

<span data-ttu-id="04ed8-104">En el ejemplo siguiente se usa una expresión regular para comprobar que una cadena tiene un formato de correo electrónico válido.</span><span class="sxs-lookup"><span data-stu-id="04ed8-104">The following example uses a regular expression to verify that a string is in valid email format.</span></span>

<span data-ttu-id="04ed8-105">Esta expresión regular es comparativamente más sencilla de lo que se puede usar realmente como un correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="04ed8-105">This regular expression is comparatively simple to what can actually be used as an email.</span></span> <span data-ttu-id="04ed8-106">Usar una expresión regular para validar un correo electrónico es útil para asegurarse de que la estructura del correo electrónico es correcta, pero no sustituye a la comprobación de que el correo electrónico existe realmente.</span><span class="sxs-lookup"><span data-stu-id="04ed8-106">Using a regular expression to validate an email is useful to make sure the structure of an email is correct, but it isn't a substitution for verifying the email actually exists.</span></span>

<span data-ttu-id="04ed8-107">✔️ Use una expresión regular pequeña para comprobar si la estructura de un correo electrónico es válida.</span><span class="sxs-lookup"><span data-stu-id="04ed8-107">✔️ DO use a small regular expression to check for the valid structure of an email.</span></span>

<span data-ttu-id="04ed8-108">✔️ Envíe un correo electrónico de prueba a la dirección proporcionada por un usuario de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="04ed8-108">✔️ DO send a test email to the address provided by a user of your app.</span></span>

<span data-ttu-id="04ed8-109">❌ No use una expresión regular como la única manera de validar un correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="04ed8-109">❌ DON'T use a regular expression as the only way you validate an email.</span></span>

<span data-ttu-id="04ed8-110">Si intenta crear la expresión regular _perfecta_ para validar que la estructura de un correo electrónico es correcta, la expresión se vuelve tan compleja que es increíblemente difícil de depurar o mejorar.</span><span class="sxs-lookup"><span data-stu-id="04ed8-110">If you try to create the _perfect_ regular expression to validate that the structure of an email is correct, the expression becomes so complex that it's incredibly difficult to debug or improve.</span></span> <span data-ttu-id="04ed8-111">Las expresiones regulares no pueden validar la existencia de un correo electrónico, incluso aunque esté estructurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="04ed8-111">Regular expressions can't validate an email exists, even if it's structured correctly.</span></span> <span data-ttu-id="04ed8-112">La mejor manera de validar un correo electrónico es enviar un mensaje de correo electrónico de prueba a la dirección.</span><span class="sxs-lookup"><span data-stu-id="04ed8-112">The best way to validate an email is to send a test email to the address.</span></span>

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="04ed8-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04ed8-113">Example</span></span>

<span data-ttu-id="04ed8-114">En el ejemplo se define un método `IsValidEmail`, que devuelve `true` si la cadena contiene una dirección de correo electrónico válida y `false` si no es válida, pero no realiza ninguna otra acción.</span><span class="sxs-lookup"><span data-stu-id="04ed8-114">The example defines an `IsValidEmail` method, which returns `true` if the string contains a valid email address and `false` if it doesn't, but takes no other action.</span></span>

<span data-ttu-id="04ed8-115">Para comprobar que la dirección de correo electrónico es válida, el método `IsValidEmail` llama al método <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> con el patrón de expresión regular `(@)(.+)$` para separar el nombre de dominio de la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="04ed8-115">To verify that the email address is valid, the `IsValidEmail` method calls the <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> method with the `(@)(.+)$` regular expression pattern to separate the domain name from the email address.</span></span> <span data-ttu-id="04ed8-116">El tercer parámetro es un delegado <xref:System.Text.RegularExpressions.MatchEvaluator> que representa el método que procesa y reemplaza el texto coincidente.</span><span class="sxs-lookup"><span data-stu-id="04ed8-116">The third parameter is a <xref:System.Text.RegularExpressions.MatchEvaluator> delegate that represents the method that processes and replaces the matched text.</span></span> <span data-ttu-id="04ed8-117">El patrón de expresión regular se interpreta de esta manera:</span><span class="sxs-lookup"><span data-stu-id="04ed8-117">The regular expression pattern is interpreted as follows.</span></span>

| <span data-ttu-id="04ed8-118">Modelo</span><span class="sxs-lookup"><span data-stu-id="04ed8-118">Pattern</span></span> | <span data-ttu-id="04ed8-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="04ed8-119">Description</span></span>                                                                         |
|---------|-------------------------------------------------------------------------------------|
| `(@)`   | <span data-ttu-id="04ed8-120">Buscar el carácter @.</span><span class="sxs-lookup"><span data-stu-id="04ed8-120">Match the @ character.</span></span> <span data-ttu-id="04ed8-121">Esta parte es el primer grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="04ed8-121">This part is the first capturing group.</span></span>                           |
| `(.+)`  | <span data-ttu-id="04ed8-122">Buscar una coincidencia con una o más apariciones de cualquier carácter.</span><span class="sxs-lookup"><span data-stu-id="04ed8-122">Match one or more occurrences of any character.</span></span> <span data-ttu-id="04ed8-123">Esta parte es el segundo grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="04ed8-123">This part is the second capturing group.</span></span> |
| `$`     | <span data-ttu-id="04ed8-124">Finalizar la búsqueda al final de la cadena.</span><span class="sxs-lookup"><span data-stu-id="04ed8-124">End the match at the end of the string.</span></span>                                             |

<span data-ttu-id="04ed8-125">El nombre de dominio junto con el carácter @ se pasa al método `DomainMapper` , que usa la clase <xref:System.Globalization.IdnMapping> para convertir los caracteres Unicode fuera del intervalo de caracteres EE.UU. - ASCII a Punycode.</span><span class="sxs-lookup"><span data-stu-id="04ed8-125">The domain name along with the @ character is passed to the `DomainMapper` method, which uses the <xref:System.Globalization.IdnMapping> class to translate Unicode characters that are outside the US-ASCII character range to Punycode.</span></span> <span data-ttu-id="04ed8-126">El método también establece la marca `invalid` en `True` si el método <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> detecta cualquier carácter no válido en el nombre del dominio.</span><span class="sxs-lookup"><span data-stu-id="04ed8-126">The method also sets the `invalid` flag to `True` if the <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> method detects any invalid characters in the domain name.</span></span> <span data-ttu-id="04ed8-127">El método devuelve el nombre de dominio Punycode precedido por el símbolo @ al método `IsValidEmail` .</span><span class="sxs-lookup"><span data-stu-id="04ed8-127">The method returns the Punycode domain name preceded by the @ symbol to the `IsValidEmail` method.</span></span>

> [!TIP]
> <span data-ttu-id="04ed8-128">Se recomienda usar el patrón de expresión regular simple `(@)(.+)$` para normalizar el dominio y devolver un valor que indique si el resultado ha sido correcto o se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="04ed8-128">It's recommended that you use use the simple `(@)(.+)$` regular expression pattern to normalize the domain and then return a value indicating that it passed or failed.</span></span> <span data-ttu-id="04ed8-129">Sin embargo, en el ejemplo de este artículo se describe cómo usar de forma avanzada una expresión regular para validar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="04ed8-129">However, the example in this article describes how to further use a regular expression to validate the email.</span></span> <span data-ttu-id="04ed8-130">Independientemente de cómo valide un correo electrónico, siempre debe enviar un correo electrónico de prueba a la dirección para asegurarse de que existe.</span><span class="sxs-lookup"><span data-stu-id="04ed8-130">Regardless of how you validate an email, you should always send a test email to the address to make sure it exists.</span></span>

<span data-ttu-id="04ed8-131">A continuación, el método `IsValidEmail` llama al método <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> para comprobar que la dirección se ajusta a un patrón de expresión regular.</span><span class="sxs-lookup"><span data-stu-id="04ed8-131">The `IsValidEmail` method then calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> method to verify that the address conforms to a regular expression pattern.</span></span>

<span data-ttu-id="04ed8-132">El método `IsValidEmail` simplemente determina si el formato del correo electrónico es válido para una dirección de correo electrónico, no valida si el correo electrónico existe.</span><span class="sxs-lookup"><span data-stu-id="04ed8-132">The `IsValidEmail` method merely determines whether the email format is valid for an email address, it doesn't validate that the email exists.</span></span> <span data-ttu-id="04ed8-133">Además, el método `IsValidEmail` no comprueba que el nombre del dominio de nivel superior sea un nombre válido enumerado en la [base de datos de la zona de la raíz de IANA](https://www.iana.org/domains/root/db), lo cual requeriría una operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="04ed8-133">Also, the `IsValidEmail` method doesn't verify that the top-level domain name is a valid domain name listed at the [IANA Root Zone Database](https://www.iana.org/domains/root/db), which would require a look-up operation.</span></span>

:::code language="csharp" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/csharp/RegexUtilities.cs":::

:::code language="vb" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/vb/RegexUtilities.vb":::

<span data-ttu-id="04ed8-134">En este ejemplo, el patrón de expresión regular `^[^@\s]+@[^@\s]+\.[^@\s]+$` se interpreta como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="04ed8-134">In this example, the regular expression pattern `^[^@\s]+@[^@\s]+\.[^@\s]+$` is interpreted as shown in the following table.</span></span> <span data-ttu-id="04ed8-135">La expresión regular se compila mediante la marca <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="04ed8-135">The regular expression is compiled using the <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> flag.</span></span>

| <span data-ttu-id="04ed8-136">Patrón</span><span class="sxs-lookup"><span data-stu-id="04ed8-136">Pattern</span></span>   | <span data-ttu-id="04ed8-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="04ed8-137">Description</span></span>                                                                              |
|-----------|------------------------------------------------------------------------------------------|
| `^`       | <span data-ttu-id="04ed8-138">Comenzar la búsqueda de coincidencia al principio de la cadena.</span><span class="sxs-lookup"><span data-stu-id="04ed8-138">Begin the match at the start of the string.</span></span>                                              |
| `[^@\s]+` | <span data-ttu-id="04ed8-139">Buscar una o más repeticiones de cualquier carácter que no sea el carácter @ o el espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="04ed8-139">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `@`       | <span data-ttu-id="04ed8-140">Buscar el carácter @.</span><span class="sxs-lookup"><span data-stu-id="04ed8-140">Match the @ character.</span></span>                                                                   |
| `[^@\s]+` | <span data-ttu-id="04ed8-141">Buscar una o más repeticiones de cualquier carácter que no sea el carácter @ o el espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="04ed8-141">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `\.`      | <span data-ttu-id="04ed8-142">Buscar un único carácter de punto.</span><span class="sxs-lookup"><span data-stu-id="04ed8-142">Match a single period character.</span></span>                                                         |
| `[^@\s]+` | <span data-ttu-id="04ed8-143">Buscar una o más repeticiones de cualquier carácter que no sea el carácter @ o el espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="04ed8-143">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `$`       | <span data-ttu-id="04ed8-144">Finalizar la búsqueda al final de la cadena.</span><span class="sxs-lookup"><span data-stu-id="04ed8-144">End the match at the end of the string.</span></span>                                                  |

> [!IMPORTANT]
> <span data-ttu-id="04ed8-145">Esta expresión regular no se ha diseñado para cubrir todos los aspectos de una dirección de correo electrónico válida.</span><span class="sxs-lookup"><span data-stu-id="04ed8-145">This regular expression is not intended to cover every aspect of a valid email address.</span></span> <span data-ttu-id="04ed8-146">Se proporciona como un ejemplo para ampliarla según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="04ed8-146">It's provided as an example for you to extend as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="04ed8-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="04ed8-147">See also</span></span>

- [<span data-ttu-id="04ed8-148">Expresiones regulares de .NET</span><span class="sxs-lookup"><span data-stu-id="04ed8-148">.NET Regular Expressions</span></span>](regular-expressions.md)
- [<span data-ttu-id="04ed8-149">¿Hasta qué punto se debe llevar la validación de direcciones de correo electrónico?</span><span class="sxs-lookup"><span data-stu-id="04ed8-149">How far should one take e-mail address validation?</span></span>](https://softwareengineering.stackexchange.com/questions/78353/how-far-should-one-take-e-mail-address-validation#78363)
