---
title: Directivas de hoja de estilos incrustadas en un documento
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 65987c5e29d593758b21259d6367202c882df2de
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45596618"
---
# <a name="style-sheet-directives-embedded-in-a-document"></a><span data-ttu-id="92ff6-102">Directivas de hoja de estilos incrustadas en un documento</span><span class="sxs-lookup"><span data-stu-id="92ff6-102">Style Sheet Directives Embedded in a Document</span></span>

<span data-ttu-id="92ff6-103">A veces, el documento XML contiene la directiva de hoja de estilos `<?xml:stylesheet?>`.</span><span class="sxs-lookup"><span data-stu-id="92ff6-103">Occasionally, existing XML contains the style sheet directive of `<?xml:stylesheet?>`.</span></span> <span data-ttu-id="92ff6-104">Microsoft Internet Explorer lo acepta como alternativa a la sintaxis `<?xml-stylesheet?>`.</span><span class="sxs-lookup"><span data-stu-id="92ff6-104">Microsoft Internet Explorer accepts this as an alternative to the `<?xml-stylesheet?>` syntax.</span></span> <span data-ttu-id="92ff6-105">Cuando los datos XML contienen una directiva `<?xml:stylesheet?>`, tal como se muestra en los datos siguientes, si se intentan cargar estos datos en el Modelo de objetos de documento XML (DOM), se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="92ff6-105">When the XML data contains an `<?xml:stylesheet?>` directive, as shown in the following data, attempting to load this data into the XML Document Object Model (DOM) throws an exception.</span></span>

```xml
<?xml version="1.0" ?>
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>
<root>
    <test>Node 1</test>
    <test>Node 2</test>
</root>
```

<span data-ttu-id="92ff6-106">Esto se produce porque `<?xml:stylesheet?>` se considera un nodo **ProcessingInstruction** no válido para DOM.</span><span class="sxs-lookup"><span data-stu-id="92ff6-106">This occurs because the `<?xml:stylesheet?>` is considered an invalid **ProcessingInstruction** to the DOM.</span></span> <span data-ttu-id="92ff6-107">Cualquier **ProcessingInstruction**, de acuerdo con la especificación XML de los espacios de nombres, solo puede ser un nombre que no incluya un signo de dos puntos (NCName), en contraposición a nombres calificados (QName).</span><span class="sxs-lookup"><span data-stu-id="92ff6-107">Any **ProcessingInstruction**, according to the Namespaces in XML specification, can only be no-colon names (NCNames), as opposed to qualified names (QNames).</span></span>

<span data-ttu-id="92ff6-108">Según la sección 6 acerca de los espacios de nombres de la especificación de XML, el efecto de los métodos **Load** y **LoadXml** que se ajustan a la especificación es que en un documento:</span><span class="sxs-lookup"><span data-stu-id="92ff6-108">From Section 6 of the Namespaces in XML specification, the effect of having the **Load** and **LoadXml** methods conform to the specification is that in a document:</span></span>

- <span data-ttu-id="92ff6-109">Todos los tipos de elemento y nombres de atributo no contienen un signo de dos puntos o sólo contienen uno.</span><span class="sxs-lookup"><span data-stu-id="92ff6-109">All element types and attribute names contain either zero or one colon.</span></span>

- <span data-ttu-id="92ff6-110">Ningún nombre de entidad, destino ProcessingInstruction ni nombre de notación, contiene un signo de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="92ff6-110">No entity names, ProcessingInstruction targets, or notation names contain any colons.</span></span>

<span data-ttu-id="92ff6-111">Si `<?xml:stylesheet?>` contiene un signo de dos puntos, se infringe la regla de la segunda viñeta.</span><span class="sxs-lookup"><span data-stu-id="92ff6-111">With the `<?xml:stylesheet?>` containing a colon, you now violate the rule in the second bullet.</span></span>

<span data-ttu-id="92ff6-112">De acuerdo con la [versión 1.0 de la recomendación sobre cómo asociar hojas de estilos con documentos XML](https://www.w3.org/TR/xml-stylesheet/) del World Wide Web Consortium (W3C), la instrucción de procesamiento para asociar una hoja de estilos XSLT con un documento XML es `<?xml-stylesheet?>`, con un guión en lugar del signo de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="92ff6-112">According to the World Wide Web Consortium (W3C) [Associating Style Sheets with XML documents Version 1.0 Recommendation](https://www.w3.org/TR/xml-stylesheet/),  the processing instruction to associate an XSLT style sheet with an XML document is `<?xml-stylesheet?>`, with a dash replacing the colon.</span></span>

## <a name="see-also"></a><span data-ttu-id="92ff6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="92ff6-113">See also</span></span>

- [<span data-ttu-id="92ff6-114">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="92ff6-114">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
