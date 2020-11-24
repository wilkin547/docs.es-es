---
title: Uso de System.Xml
ms.date: 10/22/2008
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 46282afa6548c731b04c40d8de91a1fed997c57c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677575"
---
# <a name="systemxml-usage"></a><span data-ttu-id="a8702-102">Uso de System.Xml</span><span class="sxs-lookup"><span data-stu-id="a8702-102">System.Xml Usage</span></span>

<span data-ttu-id="a8702-103">En esta sección se habla sobre el uso de varios tipos que residen en <xref:System.Xml?displayProperty=nameWithType> espacios de nombres que se pueden usar para representar datos XML.</span><span class="sxs-lookup"><span data-stu-id="a8702-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>

 <span data-ttu-id="a8702-104">❌ No use <xref:System.Xml.XmlNode> o <xref:System.Xml.XmlDocument> para representar datos XML.</span><span class="sxs-lookup"><span data-stu-id="a8702-104">❌ DO NOT use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="a8702-105">Favorece el uso de instancias de <xref:System.Xml.XPath.IXPathNavigable> , <xref:System.Xml.XmlReader> , <xref:System.Xml.XmlWriter> o subtipos de <xref:System.Xml.Linq.XNode> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a8702-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="a8702-106">`XmlNode` y `XmlDocument` no están diseñados para exponer en las API públicas.</span><span class="sxs-lookup"><span data-stu-id="a8702-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>

 <span data-ttu-id="a8702-107">✔️ utilizan `XmlReader` `IXPathNavigable` subtipos, o `XNode` como entrada o salida de miembros que aceptan o devuelven XML.</span><span class="sxs-lookup"><span data-stu-id="a8702-107">✔️ DO use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>

 <span data-ttu-id="a8702-108">Utilice estas abstracciones en lugar de `XmlDocument` , `XmlNode` o <xref:System.Xml.XPath.XPathDocument> , ya que esto desacopla los métodos de las implementaciones específicas de un documento XML en memoria y les permite trabajar con orígenes de datos XML virtuales que exponen `XNode` , `XmlReader` o <xref:System.Xml.XPath.XPathNavigator> .</span><span class="sxs-lookup"><span data-stu-id="a8702-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>

 <span data-ttu-id="a8702-109">❌ No cree subclases `XmlDocument` si desea crear un tipo que represente una vista XML de un origen de datos o un modelo de objetos subyacente.</span><span class="sxs-lookup"><span data-stu-id="a8702-109">❌ DO NOT subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>

 <span data-ttu-id="a8702-110">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="a8702-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="a8702-111">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="a8702-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="a8702-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8702-112">See also</span></span>

- [<span data-ttu-id="a8702-113">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="a8702-113">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="a8702-114">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="a8702-114">Usage Guidelines</span></span>](usage-guidelines.md)
