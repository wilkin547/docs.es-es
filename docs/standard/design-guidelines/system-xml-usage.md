---
title: Uso de System.Xml
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: c57f5451526094d58066d7d391f41795f17732de
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709041"
---
# <a name="systemxml-usage"></a><span data-ttu-id="11614-102">Uso de System.Xml</span><span class="sxs-lookup"><span data-stu-id="11614-102">System.Xml Usage</span></span>
<span data-ttu-id="11614-103">En esta sección se habla sobre el uso de varios tipos que residen en <xref:System.Xml?displayProperty=nameWithType> espacios de nombres que se pueden usar para representar datos XML.</span><span class="sxs-lookup"><span data-stu-id="11614-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>  
  
 <span data-ttu-id="11614-104">**X DO NOT** usar <xref:System.Xml.XmlNode> o <xref:System.Xml.XmlDocument> para representar los datos XML.</span><span class="sxs-lookup"><span data-stu-id="11614-104">**X DO NOT** use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="11614-105">Favorecer el uso de instancias de <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>o subtipos de <xref:System.Xml.Linq.XNode> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="11614-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="11614-106">`XmlNode` y `XmlDocument` no están diseñados para exponer en las API públicas.</span><span class="sxs-lookup"><span data-stu-id="11614-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>  
  
 <span data-ttu-id="11614-107">**✓ DO** usar `XmlReader`, `IXPathNavigable`, o subtipos de `XNode` como entrada o salida de los miembros que aceptan o devuelven XML.</span><span class="sxs-lookup"><span data-stu-id="11614-107">**✓ DO** use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>  
  
 <span data-ttu-id="11614-108">Utilice estas abstracciones en lugar de `XmlDocument`, `XmlNode`o <xref:System.Xml.XPath.XPathDocument>, porque esto desacopla los métodos de las implementaciones específicas de un documento XML en memoria y les permite trabajar con orígenes de datos XML virtuales que exponen `XNode`, `XmlReader`o <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="11614-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="11614-109">**X DO NOT** subclase `XmlDocument` si desea crear un tipo que representa una vista XML de un origen de datos o el modelo de objeto subyacente.</span><span class="sxs-lookup"><span data-stu-id="11614-109">**X DO NOT** subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>  
  
 <span data-ttu-id="11614-110">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="11614-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="11614-111">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="11614-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11614-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="11614-112">See also</span></span>

- [<span data-ttu-id="11614-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="11614-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="11614-114">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="11614-114">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
