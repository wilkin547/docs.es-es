---
title: Asignación de tipos de datos XML a tipos CLR
ms.date: 03/30/2017
ms.assetid: cabdfcad-f359-479b-b71c-8b2fad42ca49
ms.openlocfilehash: 1a79d178a4e027973591061634cfb5904dd3e0cc
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822586"
---
# <a name="mapping-xml-data-types-to-clr-types"></a><span data-ttu-id="508b5-102">Asignación de tipos de datos XML a tipos CLR</span><span class="sxs-lookup"><span data-stu-id="508b5-102">Mapping XML Data Types to CLR Types</span></span>

<span data-ttu-id="508b5-103">En la siguiente tabla se describen las asignaciones predeterminadas entre tipos de datos XML y los tipos Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="508b5-103">The following table describes the default mapping between the XML data types and the common language runtime (CLR) types.</span></span>

> [!NOTE]
> <span data-ttu-id="508b5-104">Los prefijos `xs` y `xdt` se asignan a los identificadores URI de espacios de nombres <https://www.w3.org/2001/XMLSchema> y <https://www.w3.org/2003/05/xpath-datatypes> respectivamente.</span><span class="sxs-lookup"><span data-stu-id="508b5-104">The `xs` and the `xdt` prefixes are mapped to the <https://www.w3.org/2001/XMLSchema> and the <https://www.w3.org/2003/05/xpath-datatypes> namespace URIs respectively.</span></span>

|<span data-ttu-id="508b5-105">Tipo XML</span><span class="sxs-lookup"><span data-stu-id="508b5-105">XML Type</span></span>|<span data-ttu-id="508b5-106">Tipo CLR</span><span class="sxs-lookup"><span data-stu-id="508b5-106">CLR Type</span></span>|
|--------------|--------------|
|`xs:anyURI`|<xref:System.Uri>|
|`xs:base64Binary`|`Byte[]`|
|`xs:boolean`|<xref:System.Boolean>|
|`xs:byte`|<xref:System.SByte>|
|`xs:date`|<xref:System.DateTime>|
|`xs:dateTime`|<xref:System.DateTime>|
|`xs:decimal`|<xref:System.Decimal>|
|`xs:double`|<xref:System.Double>|
|`xs:duration`|<xref:System.TimeSpan>|
|`xs:ENTITIES`|`String[]`|
|`xs:ENTITY`|<xref:System.String>|
|`xs:float`|<xref:System.Single>|
|`xs:gDay`|<xref:System.DateTime>|
|`xs:gMonthDay`|<xref:System.DateTime>|
|`xs:gYear`|<xref:System.DateTime>|
|`xs:gYearMonth`|<xref:System.DateTime>|
|`xs:hexBinary`|`Byte[]`|
|`xs:ID`|<xref:System.String>|
|`xs:IDREF`|<xref:System.String>|
|`xs:IDREFS`|`String[]`|
|`xs:int`|<xref:System.Int32>|
|`xs:integer`|<xref:System.Decimal>|
|`xs:language`|<xref:System.String>|
|`xs:long`|<xref:System.Int64>|
|`xs:gMonth`|<xref:System.DateTime>|
|`xs:Name`|<xref:System.String>|
|`xs:NCName`|<xref:System.String>|
|`xs:negativeInteger`|<xref:System.Decimal>|
|`xs:NMTOKEN`|<xref:System.String>|
|`xs:NMTOKENS`|`String[]`|
|`xs:nonNegativeInteger`|<xref:System.Decimal>|
|`xs:nonPositiveInteger`|<xref:System.Decimal>|
|`xs:normalizedString`|<xref:System.String>|
|`xs:NOTATION`|<xref:System.Xml.XmlQualifiedName>|
|`xs:positiveInteger`|<xref:System.Decimal>|
|`xs:QName`|<xref:System.Xml.XmlQualifiedName>|
|`xs:short`|<xref:System.Int16>|
|`xs:string`|<xref:System.String>|
|`xs:time`|<xref:System.DateTime>|
|`xs:token`|<xref:System.String>|
|`xs:unsignedByte`|<xref:System.Byte>|
|`xs:unsignedInt`|<xref:System.UInt32>|
|`xs:unsignedLong`|<xref:System.UInt64>|
|`xs:unsignedShort`|<xref:System.UInt16>|
|`xdt:dayTimeDuration`|<xref:System.TimeSpan>|
|`xdt:yearMonthDuration`|<xref:System.TimeSpan>|
|`xdt:untypedAtomic`|<xref:System.String>|
|`xdt:anyAtomicType`|<xref:System.Object>|
|`xs:anySimpleType`|<xref:System.String>|
|<span data-ttu-id="508b5-107">Nodo de documento</span><span class="sxs-lookup"><span data-stu-id="508b5-107">Document node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|
|<span data-ttu-id="508b5-108">Nodo de elementos</span><span class="sxs-lookup"><span data-stu-id="508b5-108">Element node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|
|<span data-ttu-id="508b5-109">Nodo de atributos</span><span class="sxs-lookup"><span data-stu-id="508b5-109">Attribute node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|
|<span data-ttu-id="508b5-110">Nodo de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="508b5-110">Namespace node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|
|<span data-ttu-id="508b5-111">Nodo de texto</span><span class="sxs-lookup"><span data-stu-id="508b5-111">Text node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|
|<span data-ttu-id="508b5-112">Nodo de comentarios</span><span class="sxs-lookup"><span data-stu-id="508b5-112">Comment node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|
|<span data-ttu-id="508b5-113">Nodo de instrucción de procesamiento</span><span class="sxs-lookup"><span data-stu-id="508b5-113">Processing instruction node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|

## <a name="see-also"></a><span data-ttu-id="508b5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="508b5-114">See also</span></span>

- [<span data-ttu-id="508b5-115">Compatibilidad de tipos en las clases System.Xml</span><span class="sxs-lookup"><span data-stu-id="508b5-115">Type Support in the System.Xml Classes</span></span>](type-support-in-the-system-xml-classes.md)
