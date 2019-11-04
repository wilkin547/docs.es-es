---
title: x:XData (Tipo XAML intrínseco)
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: 8496e7c87cf7e6eea996ca7af4f288b7495c7661
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459903"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="5caef-102">x:XData (Tipo XAML intrínseco)</span><span class="sxs-lookup"><span data-stu-id="5caef-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="5caef-103">Habilita la colocación de las islas de datos XML dentro de un entorno de producción XAML.</span><span class="sxs-lookup"><span data-stu-id="5caef-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="5caef-104">Los elementos XML dentro de `x:XData` no deben ser tratados por procesadores XAML como si formaran parte del espacio de nombres XAML predeterminado de la acción o cualquier otro espacio de nombres XAML.</span><span class="sxs-lookup"><span data-stu-id="5caef-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="5caef-105">`x:XData` puede contener XML con formato correcto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="5caef-105">`x:XData` can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="5caef-106">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="5caef-106">XAML Object Element Usage</span></span>  
  
```xaml  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="5caef-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="5caef-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="5caef-108">Elemento raíz único de la isla de datos delimitada.</span><span class="sxs-lookup"><span data-stu-id="5caef-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="5caef-109">Para la mayoría de los consumidores eventuales, XML que no tiene una sola raíz se considera no válido.</span><span class="sxs-lookup"><span data-stu-id="5caef-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="5caef-110">En concreto, se requiere una sola raíz si el `x:XData` está pensado como un origen de datos XML para WPF o muchas otras tecnologías que usan orígenes XML para el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="5caef-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="5caef-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5caef-111">Optional.</span></span> <span data-ttu-id="5caef-112">XML que representa los datos XML.</span><span class="sxs-lookup"><span data-stu-id="5caef-112">XML that represents the XML data.</span></span> <span data-ttu-id="5caef-113">Se puede incluir cualquier número de elementos como datos de elemento y los elementos anidados pueden estar contenidos en otros elementos; sin embargo, se aplican las reglas generales de XML.</span><span class="sxs-lookup"><span data-stu-id="5caef-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5caef-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5caef-114">Remarks</span></span>  
 <span data-ttu-id="5caef-115">Los elementos XML dentro de un objeto `x:XData` pueden volver a declarar todos los espacios de nombres y prefijos posibles del que contiene XMLDOM dentro de los datos.</span><span class="sxs-lookup"><span data-stu-id="5caef-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="5caef-116">El acceso mediante programación a los datos XML y el tipo XAML intrínseco `x:XData` es posible en .NET Framework servicios XAML a través de la clase <xref:System.Windows.Markup.XData>.</span><span class="sxs-lookup"><span data-stu-id="5caef-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="5caef-117">Notas de uso de WPF</span><span class="sxs-lookup"><span data-stu-id="5caef-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="5caef-118">El objeto `x:XData` se utiliza principalmente como un objeto secundario de un <xref:System.Windows.Data.XmlDataProvider>, o como alternativa, como el objeto secundario de la propiedad <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> (en XAML, normalmente se expresa en sintaxis de elementos de propiedad).</span><span class="sxs-lookup"><span data-stu-id="5caef-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="5caef-119">Normalmente, los datos deben volver a definir el espacio de nombres XML base dentro de la isla de datos para que sea un nuevo espacio de nombres XML predeterminado (establecido en una cadena vacía).</span><span class="sxs-lookup"><span data-stu-id="5caef-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="5caef-120">Esto es más fácil para las islas de datos simples porque las expresiones <xref:System.Windows.Data.Binding.XPath%2A> que se usan para hacer referencia y enlazar a los datos pueden evitar la inclusión de prefijos.</span><span class="sxs-lookup"><span data-stu-id="5caef-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="5caef-121">Las islas de datos más complejas pueden definir varios prefijos para los datos y usar un prefijo específico para el espacio de nombres XML en la raíz.</span><span class="sxs-lookup"><span data-stu-id="5caef-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="5caef-122">En este caso, todas las referencias de expresión de <xref:System.Windows.Data.Binding.XPath%2A> deben incluir el prefijo asignado por espacio de nombres adecuado.</span><span class="sxs-lookup"><span data-stu-id="5caef-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="5caef-123">Para obtener más información, consulte [Información general sobre el enlace de datos](../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5caef-123">For more information, see [Data Binding Overview](../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="5caef-124">Técnicamente, `x:XData` se puede utilizar como contenido de cualquier propiedad de tipo <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="5caef-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="5caef-125">Sin embargo, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> es la única implementación destacada.</span><span class="sxs-lookup"><span data-stu-id="5caef-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5caef-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5caef-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="5caef-127">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="5caef-127">Data Binding Overview</span></span>](../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="5caef-128">Binding (extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="5caef-128">Binding Markup Extension</span></span>](../wpf/advanced/binding-markup-extension.md)
