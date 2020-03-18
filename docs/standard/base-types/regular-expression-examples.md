---
title: Ejemplos de expresiones regulares
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- regular expressions [.NET Framework], examples
- regular expressions [.NET Framework]
- strings [.NET Framework], regular expressions
ms.assetid: e9fd53f2-ed56-4b09-b2ea-e9bc9d65e6d6
ms.openlocfilehash: 788fa2a6793e14189def4c30a0baf0d4a5cf6b0a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73128095"
---
# <a name="regular-expression-examples"></a><span data-ttu-id="9864d-102">Ejemplos de expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="9864d-102">Regular Expression Examples</span></span>
<span data-ttu-id="9864d-103">Esta sección contiene ejemplos de código que ilustran el uso de expresiones regulares en aplicaciones comunes.</span><span class="sxs-lookup"><span data-stu-id="9864d-103">This section contains code examples that illustrate the use of regular expressions in common applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9864d-104">El espacio de nombres <xref:System.Web.RegularExpressions> contiene un número de objetos de expresión regular que implementan modelos de expresión regular predefinidos para el análisis de cadenas a partir de documentos HTML, XML y ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9864d-104">The <xref:System.Web.RegularExpressions> namespace contains a number of regular expression objects that implement predefined regular expression patterns for parsing strings from HTML, XML, and ASP.NET documents.</span></span> <span data-ttu-id="9864d-105">Por ejemplo, la clase <xref:System.Web.RegularExpressions.TagRegex> identifica las etiquetas de inicio en una cadena y la clase <xref:System.Web.RegularExpressions.CommentRegex> identifica los comentarios de ASP.NET en una cadena.</span><span class="sxs-lookup"><span data-stu-id="9864d-105">For example, the <xref:System.Web.RegularExpressions.TagRegex> class identifies start tags in a string and the <xref:System.Web.RegularExpressions.CommentRegex> class identifies ASP.NET comments in a string.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9864d-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9864d-106">In This Section</span></span>  
 [<span data-ttu-id="9864d-107">Ejemplo: Buscar etiquetas HREF</span><span class="sxs-lookup"><span data-stu-id="9864d-107">Example: Scanning for HREFs</span></span>](../../../docs/standard/base-types/regular-expression-example-scanning-for-hrefs.md)  
 <span data-ttu-id="9864d-108">Ofrece un ejemplo en el que se busca una cadena de entrada y se muestran todos los valores href="…" y sus ubicaciones en la cadena.</span><span class="sxs-lookup"><span data-stu-id="9864d-108">Provides an example that searches an input string and prints out all the href="…" values and their locations in the string.</span></span>  
  
 [<span data-ttu-id="9864d-109">Ejemplo: Cambiar formatos de fecha</span><span class="sxs-lookup"><span data-stu-id="9864d-109">Example: Changing Date Formats</span></span>](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md)  
 <span data-ttu-id="9864d-110">Ofrece un ejemplo en el que se reemplazan las fechas en formato mm/dd/aa por fechas en el formato dd-mm-aa.</span><span class="sxs-lookup"><span data-stu-id="9864d-110">Provides an example that replaces dates in the form mm/dd/yy with dates in the form dd-mm-yy.</span></span>  
  
 [<span data-ttu-id="9864d-111">Extraer un protocolo y un número de puerto de una dirección URL</span><span class="sxs-lookup"><span data-stu-id="9864d-111">How to: Extract a Protocol and Port Number from a URL</span></span>](../../../docs/standard/base-types/how-to-extract-a-protocol-and-port-number-from-a-url.md)  
 <span data-ttu-id="9864d-112">Ofrece un ejemplo en el que se extrae un protocolo y número de puerto de una cadena que contiene una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="9864d-112">Provides an example that extracts a protocol and port number from a string that contains a URL.</span></span> <span data-ttu-id="9864d-113">Por ejemplo, "http://www.contoso.com:8080/letters/readme.html" devuelve "http:8080".</span><span class="sxs-lookup"><span data-stu-id="9864d-113">For example, "http://www.contoso.com:8080/letters/readme.html" returns "http:8080".</span></span>  
  
 [<span data-ttu-id="9864d-114">Quitar caracteres no válidos de una cadena</span><span class="sxs-lookup"><span data-stu-id="9864d-114">How to: Strip Invalid Characters from a String</span></span>](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md)  
 <span data-ttu-id="9864d-115">Ofrece un ejemplo en el que se eliminan los caracteres no alfanuméricos no válidos de una cadena.</span><span class="sxs-lookup"><span data-stu-id="9864d-115">Provides an example that strips invalid non-alphanumeric characters from a string.</span></span>  
  
 [<span data-ttu-id="9864d-116">Comprobar si las cadenas tienen un formato de correo electrónico válido</span><span class="sxs-lookup"><span data-stu-id="9864d-116">How to: Verify that Strings Are in Valid Email Format</span></span>](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)  
 <span data-ttu-id="9864d-117">Proporciona un ejemplo que comprueba si una cadena tiene un formato de correo electrónico válido.</span><span class="sxs-lookup"><span data-stu-id="9864d-117">Provides an example that verifies that a string is in valid email format.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9864d-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="9864d-118">Reference</span></span>  
 <xref:System.Text.RegularExpressions>  
 <span data-ttu-id="9864d-119">Ofrece información de referencia de la biblioteca de clases para el espacio de nombres **System.Text.RegularExpressions** de .NET.</span><span class="sxs-lookup"><span data-stu-id="9864d-119">Provides class library reference information for the .NET **System.Text.RegularExpressions** namespace.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9864d-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="9864d-120">Related Sections</span></span>  
 [<span data-ttu-id="9864d-121">Expresiones regulares de .NET</span><span class="sxs-lookup"><span data-stu-id="9864d-121">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="9864d-122">Proporciona información general sobre el aspecto del lenguaje de programación de expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="9864d-122">Provides an overview of the programming language aspect of regular expressions.</span></span>  
  
 [<span data-ttu-id="9864d-123">Modelo de objetos de expresión regular</span><span class="sxs-lookup"><span data-stu-id="9864d-123">The Regular Expression Object Model</span></span>](../../../docs/standard/base-types/the-regular-expression-object-model.md)  
 <span data-ttu-id="9864d-124">Describe las clases de expresión regular contenidas en el espacio de nombres `System.Text.RegularExpression` y proporciona ejemplos de su uso.</span><span class="sxs-lookup"><span data-stu-id="9864d-124">Describes the regular expression classes contained in the `System.Text.RegularExpression` namespace and provides examples of their use.</span></span>  
  
 [<span data-ttu-id="9864d-125">Detalles del comportamiento de expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="9864d-125">Details of Regular Expression Behavior</span></span>](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)  
 <span data-ttu-id="9864d-126">Proporciona información sobre las funcionalidades y el comportamiento de las expresiones regulares de .NET.</span><span class="sxs-lookup"><span data-stu-id="9864d-126">Provides information about the capabilities and behavior of .NET regular expressions.</span></span>  
  
 [<span data-ttu-id="9864d-127">Lenguaje de expresiones regulares: referencia rápida</span><span class="sxs-lookup"><span data-stu-id="9864d-127">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 <span data-ttu-id="9864d-128">Ofrece información sobre el conjunto de caracteres, operadores y construcciones que se pueden utilizar para definir expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="9864d-128">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
