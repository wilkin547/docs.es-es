---
title: "x:XData (Tipo XAML intrínseco)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
caps.latest.revision: "17"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 3e448c28be6515748254e267b70f3c898b9226a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="a6169-102">x:XData (Tipo XAML intrínseco)</span><span class="sxs-lookup"><span data-stu-id="a6169-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="a6169-103">Permite la colocación de XML, Islas de datos dentro de una producción de XAML.</span><span class="sxs-lookup"><span data-stu-id="a6169-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="a6169-104">Elementos XML dentro de `x:XData` no deben tratarse por los procesadores XAML como si fueran una parte del espacio de nombres XAML de manera predeterminada de actuar o cualquier otro espacio de nombres XAML.</span><span class="sxs-lookup"><span data-stu-id="a6169-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="a6169-105">`x:XData`puede contener código XML arbitrario con formato correcto.</span><span class="sxs-lookup"><span data-stu-id="a6169-105">`x:XData` can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="a6169-106">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="a6169-106">XAML Object Element Usage</span></span>  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="a6169-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="a6169-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="a6169-108">El elemento raíz único de la isla de datos adjunta.</span><span class="sxs-lookup"><span data-stu-id="a6169-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="a6169-109">Para la mayoría de los consumidores eventuales, XML que no tiene una raíz se considera no válida.</span><span class="sxs-lookup"><span data-stu-id="a6169-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="a6169-110">En concreto, una única raíz es necesaria si la `x:XData` está pensado como un origen de datos XML para WPF o muchas otras tecnologías que usan orígenes de XML para el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="a6169-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="a6169-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a6169-111">Optional.</span></span> <span data-ttu-id="a6169-112">Código XML que representa los datos XML.</span><span class="sxs-lookup"><span data-stu-id="a6169-112">XML that represents the XML data.</span></span> <span data-ttu-id="a6169-113">Puede contener cualquier número de elementos como los datos del elemento y los elementos anidados pueden estar contenidos en otros elementos; Sin embargo, se aplican las reglas generales de XML.</span><span class="sxs-lookup"><span data-stu-id="a6169-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6169-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6169-114">Remarks</span></span>  
 <span data-ttu-id="a6169-115">Los elementos XML dentro de un `x:XData` objeto puede volver a declarar todos los posibles espacios de nombres y prefijos del contenedor XMLDOM dentro de los datos.</span><span class="sxs-lookup"><span data-stu-id="a6169-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="a6169-116">Acceso mediante programación a los datos XML y la `x:XData` tipo XAML intrínseco es posible en los servicios XAML de .NET Framework a través de la <xref:System.Windows.Markup.XData> clase.</span><span class="sxs-lookup"><span data-stu-id="a6169-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="a6169-117">Notas de uso WPF</span><span class="sxs-lookup"><span data-stu-id="a6169-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="a6169-118">El `x:XData` objeto se usa principalmente como un objeto secundario de un <xref:System.Windows.Data.XmlDataProvider>, o bien, como el objeto secundario de la <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> propiedad (en XAML, esto se expresa normalmente en la sintaxis de elemento de propiedad).</span><span class="sxs-lookup"><span data-stu-id="a6169-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="a6169-119">Los datos normalmente deben volver a definir el espacio de nombres XML base dentro de la isla de datos como un nuevo espacio de nombres XML (establecido en una cadena vacía).</span><span class="sxs-lookup"><span data-stu-id="a6169-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="a6169-120">Esto es más fácil para islas de datos simple porque la <xref:System.Windows.Data.Binding.XPath%2A> expresiones que se usan para hacer referencia y enlazar a los datos pueden evitar la inclusión de prefijos.</span><span class="sxs-lookup"><span data-stu-id="a6169-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="a6169-121">Islas de datos más complejas pueden definir varios prefijos para los datos y usar un prefijo concreto para el espacio de nombres XML en la raíz.</span><span class="sxs-lookup"><span data-stu-id="a6169-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="a6169-122">En este caso, todas las <xref:System.Windows.Data.Binding.XPath%2A> las referencias a expresiones deben incluir el prefijo de espacio de nombres asignado adecuado.</span><span class="sxs-lookup"><span data-stu-id="a6169-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="a6169-123">Para obtener más información, consulte [Información general sobre el enlace de datos](../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a6169-123">For more information, see [Data Binding Overview](../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="a6169-124">Técnicamente, `x:XData` puede utilizarse como el contenido de cualquier propiedad de tipo <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="a6169-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="a6169-125">Sin embargo, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> es la única implementación notable.</span><span class="sxs-lookup"><span data-stu-id="a6169-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6169-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6169-126">See Also</span></span>  
 <xref:System.Windows.Data.XmlDataProvider>  
 [<span data-ttu-id="a6169-127">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="a6169-127">Data Binding Overview</span></span>](../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="a6169-128">Binding (extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="a6169-128">Binding Markup Extension</span></span>](../../../docs/framework/wpf/advanced/binding-markup-extension.md)
