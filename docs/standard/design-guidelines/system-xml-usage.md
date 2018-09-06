---
title: Uso de System.Xml
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c3eb01e1050bc78d2b31de19a8a728af92777e8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863392"
---
# <a name="systemxml-usage"></a><span data-ttu-id="d1bef-102">Uso de System.Xml</span><span class="sxs-lookup"><span data-stu-id="d1bef-102">System.Xml Usage</span></span>
<span data-ttu-id="d1bef-103">Esta sección se habla sobre el uso de varios tipos que se encuentran en <xref:System.Xml?displayProperty=nameWithType> espacios de nombres que se pueden usar para representar los datos XML.</span><span class="sxs-lookup"><span data-stu-id="d1bef-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>  
  
 <span data-ttu-id="d1bef-104">**X DO NOT** usar <xref:System.Xml.XmlNode> o <xref:System.Xml.XmlDocument> para representar los datos XML.</span><span class="sxs-lookup"><span data-stu-id="d1bef-104">**X DO NOT** use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="d1bef-105">Favorecer el uso de las instancias de <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, o los subtipos de <xref:System.Xml.Linq.XNode> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d1bef-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="d1bef-106">`XmlNode` y `XmlDocument` no están diseñados para exponer en las API públicas.</span><span class="sxs-lookup"><span data-stu-id="d1bef-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>  
  
 <span data-ttu-id="d1bef-107">**✓ DO** usar `XmlReader`, `IXPathNavigable`, o subtipos de `XNode` como entrada o salida de los miembros que aceptan o devuelven XML.</span><span class="sxs-lookup"><span data-stu-id="d1bef-107">**✓ DO** use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>  
  
 <span data-ttu-id="d1bef-108">Utilice estas abstracciones en lugar de `XmlDocument`, `XmlNode`, o <xref:System.Xml.XPath.XPathDocument>, ya que esto desacopla los métodos de implementaciones específicas de un documento XML en memoria y se les permite trabajar con orígenes de datos XML virtuales que exponen `XNode` , `XmlReader`, o <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="d1bef-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="d1bef-109">**X DO NOT** subclase `XmlDocument` si desea crear un tipo que representa una vista XML de un origen de datos o el modelo de objeto subyacente.</span><span class="sxs-lookup"><span data-stu-id="d1bef-109">**X DO NOT** subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>  
  
 <span data-ttu-id="d1bef-110">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="d1bef-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d1bef-111">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="d1bef-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1bef-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1bef-112">See also</span></span>

- [<span data-ttu-id="d1bef-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d1bef-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="d1bef-114">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="d1bef-114">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
