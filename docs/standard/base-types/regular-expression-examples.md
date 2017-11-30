---
title: Ejemplos de expresiones regulares
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- regular expressions [.NET Framework], examples
- regular expressions [.NET Framework]
- strings [.NET Framework], regular expressions
ms.assetid: e9fd53f2-ed56-4b09-b2ea-e9bc9d65e6d6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d7fa8fe2bade9f20f71f846c717d79d6b6ffb36
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-examples"></a><span data-ttu-id="4ff16-102">Ejemplos de expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="4ff16-102">Regular Expression Examples</span></span>
<span data-ttu-id="4ff16-103">Esta sección contiene ejemplos de código que ilustran el uso de expresiones regulares en aplicaciones comunes.</span><span class="sxs-lookup"><span data-stu-id="4ff16-103">This section contains code examples that illustrate the use of regular expressions in common applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ff16-104">El <xref:System.Web.RegularExpressions> espacio de nombres contiene un número de objetos de expresión regular que implementan patrones de expresión regular predefinido para el análisis de cadenas a partir de documentos HTML, XML y ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4ff16-104">The <xref:System.Web.RegularExpressions> namespace contains a number of regular expression objects that implement predefined regular expression patterns for parsing strings from HTML, XML, and ASP.NET documents.</span></span> <span data-ttu-id="4ff16-105">Por ejemplo, el <xref:System.Web.RegularExpressions.TagRegex> clase identifica las etiquetas de inicio en una cadena y la <xref:System.Web.RegularExpressions.CommentRegex> clase identifica los comentarios de ASP.NET en una cadena.</span><span class="sxs-lookup"><span data-stu-id="4ff16-105">For example, the <xref:System.Web.RegularExpressions.TagRegex> class identifies start tags in a string and the <xref:System.Web.RegularExpressions.CommentRegex> class identifies ASP.NET comments in a string.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ff16-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4ff16-106">In This Section</span></span>  
 [<span data-ttu-id="4ff16-107">Ejemplo: Buscar etiquetas HREF</span><span class="sxs-lookup"><span data-stu-id="4ff16-107">Example: Scanning for HREFs</span></span>](../../../docs/standard/base-types/regular-expression-example-scanning-for-hrefs.md)  
 <span data-ttu-id="4ff16-108">Proporciona un ejemplo que busca una cadena de entrada e imprime todo el href = "..." valores y sus ubicaciones en la cadena.</span><span class="sxs-lookup"><span data-stu-id="4ff16-108">Provides an example that searches an input string and prints out all the href="…" values and their locations in the string.</span></span>  
  
 [<span data-ttu-id="4ff16-109">Ejemplo: Cambiar formatos de fecha</span><span class="sxs-lookup"><span data-stu-id="4ff16-109">Example: Changing Date Formats</span></span>](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md)  
 <span data-ttu-id="4ff16-110">Proporciona un ejemplo que reemplaza las fechas en formato mm/dd/aa con fechas en el formato dd-mm-aa..</span><span class="sxs-lookup"><span data-stu-id="4ff16-110">Provides an example that replaces dates in the form mm/dd/yy with dates in the form dd-mm-yy.</span></span>  
  
 [<span data-ttu-id="4ff16-111">Extraer un protocolo y un número de puerto de una dirección URL</span><span class="sxs-lookup"><span data-stu-id="4ff16-111">How to: Extract a Protocol and Port Number from a URL</span></span>](../../../docs/standard/base-types/how-to-extract-a-protocol-and-port-number-from-a-url.md)  
 <span data-ttu-id="4ff16-112">Proporciona un ejemplo que extrae un protocolo y número de puerto de una cadena que contiene una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="4ff16-112">Provides an example that extracts a protocol and port number from a string that contains a URL.</span></span> <span data-ttu-id="4ff16-113">Por ejemplo, "http://www.contoso.com:8080/letters/readme.html" devuelve "http:8080".</span><span class="sxs-lookup"><span data-stu-id="4ff16-113">For example, "http://www.contoso.com:8080/letters/readme.html" returns "http:8080".</span></span>  
  
 [<span data-ttu-id="4ff16-114">Quitar caracteres no válidos de una cadena</span><span class="sxs-lookup"><span data-stu-id="4ff16-114">How to: Strip Invalid Characters from a String</span></span>](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md)  
 <span data-ttu-id="4ff16-115">Proporciona un ejemplo que quita los caracteres no alfanuméricos no válidos de una cadena.</span><span class="sxs-lookup"><span data-stu-id="4ff16-115">Provides an example that strips invalid non-alphanumeric characters from a string.</span></span>  
  
 [<span data-ttu-id="4ff16-116">Comprobar si las cadenas tienen un formato de correo electrónico válido</span><span class="sxs-lookup"><span data-stu-id="4ff16-116">How to: Verify that Strings Are in Valid Email Format</span></span>](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)  
 <span data-ttu-id="4ff16-117">Proporciona un ejemplo que puede usar para comprobar que es una cadena en formato de correo electrónico válida.</span><span class="sxs-lookup"><span data-stu-id="4ff16-117">Provides an example that you can use to verify that a string is in valid email format.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4ff16-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="4ff16-118">Reference</span></span>  
 <xref:System.Text.RegularExpressions>  
 <span data-ttu-id="4ff16-119">Proporciona información de referencia de la biblioteca de clases para .NET **System.Text.RegularExpressions** espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4ff16-119">Provides class library reference information for the .NET **System.Text.RegularExpressions** namespace.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4ff16-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4ff16-120">Related Sections</span></span>  
 [<span data-ttu-id="4ff16-121">Expresiones regulares de .NET</span><span class="sxs-lookup"><span data-stu-id="4ff16-121">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="4ff16-122">Proporciona información general sobre el aspecto del lenguaje de programación de expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="4ff16-122">Provides an overview of the programming language aspect of regular expressions.</span></span>  
  
 [<span data-ttu-id="4ff16-123">Modelo de objetos de expresión regular</span><span class="sxs-lookup"><span data-stu-id="4ff16-123">The Regular Expression Object Model</span></span>](../../../docs/standard/base-types/the-regular-expression-object-model.md)  
 <span data-ttu-id="4ff16-124">Describe las clases de expresiones regulares contenidas en el `System.Text.RegularExpression` espacio de nombres y proporciona ejemplos de su uso.</span><span class="sxs-lookup"><span data-stu-id="4ff16-124">Describes the regular expression classes contained in the `System.Text.RegularExpression` namespace and provides examples of their use.</span></span>  
  
 [<span data-ttu-id="4ff16-125">Detalles del comportamiento de expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="4ff16-125">Details of Regular Expression Behavior</span></span>](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)  
 <span data-ttu-id="4ff16-126">Proporciona información sobre las características y comportamiento de expresiones regulares. NET.</span><span class="sxs-lookup"><span data-stu-id="4ff16-126">Provides information about the capabilities and behavior of .NET regular expressions.</span></span>  
  
 [<span data-ttu-id="4ff16-127">Lenguaje de expresiones regulares: referencia rápida</span><span class="sxs-lookup"><span data-stu-id="4ff16-127">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 <span data-ttu-id="4ff16-128">Ofrece información sobre el conjunto de caracteres, operadores y construcciones que se pueden utilizar para definir expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="4ff16-128">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
