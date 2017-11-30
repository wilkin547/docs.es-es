---
title: Directivas de hoja de estilos incrustadas en un documento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c5cfcc9f35e4a07e9426a4dd24c1e2f04985f16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="style-sheet-directives-embedded-in-a-document"></a><span data-ttu-id="7cf97-102">Directivas de hoja de estilos incrustadas en un documento</span><span class="sxs-lookup"><span data-stu-id="7cf97-102">Style Sheet Directives Embedded in a Document</span></span>
<span data-ttu-id="7cf97-103">A veces, el documento XML contiene la directiva de hoja de estilos `<?xml:stylesheet?>`.</span><span class="sxs-lookup"><span data-stu-id="7cf97-103">Occasionally, existing XML contains the style sheet directive of `<?xml:stylesheet?>`.</span></span> <span data-ttu-id="7cf97-104">Microsoft Internet Explorer lo acepta como alternativa a la `<?xml-stylesheet?>` sintaxis.</span><span class="sxs-lookup"><span data-stu-id="7cf97-104">Microsoft Internet Explorer accepts this as an alternative to the `<?xml-stylesheet?>` syntax.</span></span> <span data-ttu-id="7cf97-105">Cuando los datos XML contienen una directiva `<?xml:stylesheet?>`, tal como se muestra en los datos siguientes, si se intentan cargar estos datos en el Modelo de objetos de documento XML (DOM), se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="7cf97-105">When the XML data contains an `<?xml:stylesheet?>` directive, as shown in the following data, attempting to load this data into the XML Document Object Model (DOM) throws an exception.</span></span>  
  
```xml  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 <span data-ttu-id="7cf97-106">Esto ocurre porque la `<?xml:stylesheet?>` se considera no válido **ProcessingInstruction** en el DOM.</span><span class="sxs-lookup"><span data-stu-id="7cf97-106">This occurs because the `<?xml:stylesheet?>` is considered an invalid **ProcessingInstruction** to the DOM.</span></span> <span data-ttu-id="7cf97-107">Cualquier **ProcessingInstruction**, según los espacios de nombres en la especificación XML, solo pueden ser nombres sin dos puntos (NCName), en contraposición a completo nombres (completos QName).</span><span class="sxs-lookup"><span data-stu-id="7cf97-107">Any **ProcessingInstruction**, according to the Namespaces in XML specification, can only be no-colon names (NCNames), as opposed to qualified names (QNames).</span></span>  
  
 <span data-ttu-id="7cf97-108">Desde la sección 6 acerca de los espacios de nombres en la especificación de XML, el efecto de tener la **carga** y **LoadXml** métodos se ajustan a la especificación es que en un documento:</span><span class="sxs-lookup"><span data-stu-id="7cf97-108">From Section 6 of the Namespaces in XML specification, the effect of having the **Load** and **LoadXml** methods conform to the specification is that in a document:</span></span>  
  
-   <span data-ttu-id="7cf97-109">Todos los tipos de elemento y nombres de atributo no contienen un signo de dos puntos o sólo contienen uno.</span><span class="sxs-lookup"><span data-stu-id="7cf97-109">All element types and attribute names contain either zero or one colon.</span></span>  
  
-   <span data-ttu-id="7cf97-110">Ningún nombre de entidad, destino ProcessingInstruction ni nombre de notación, contiene un signo de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="7cf97-110">No entity names, ProcessingInstruction targets, or notation names contain any colons.</span></span>  
  
 <span data-ttu-id="7cf97-111">Si `<?xml:stylesheet?>` contiene un signo de dos puntos, se infringe la regla de la segunda viñeta.</span><span class="sxs-lookup"><span data-stu-id="7cf97-111">With the `<?xml:stylesheet?>` containing a colon, you now violate the rule in the second bullet.</span></span>  
  
 <span data-ttu-id="7cf97-112">De acuerdo con la recomendación de la versión 1,0 de los documentos XML acerca de la asociación de hojas de estilos de W3C, que se encuentra en www.w3.org/TR/xml-stylesheet, la instrucción de procesamiento para asociar una hoja de estilos XSLT con un documento XML es `<?xml-stylesheet?>`, con un guión en lugar del signo de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="7cf97-112">According to the World Wide Web Consortium (W3C) Associating Style Sheets with XML documents Version 1.0 Recommendation, located at www.w3.org/TR/xml-stylesheet, the processing instruction to associate an XSLT style sheet with an XML document is `<?xml-stylesheet?>`, with a dash replacing the colon.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf97-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cf97-113">See Also</span></span>  
 [<span data-ttu-id="7cf97-114">Modelo de objetos de documento (DOM) de XML</span><span class="sxs-lookup"><span data-stu-id="7cf97-114">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
