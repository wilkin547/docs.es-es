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
ms.openlocfilehash: d78c2fd63192dc499b119e5b038b92555511a695
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544809"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="5e673-102">x:XData (Tipo XAML intrínseco)</span><span class="sxs-lookup"><span data-stu-id="5e673-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="5e673-103">Habilita la colocación de las islas de datos XML dentro de un entorno de producción XAML.</span><span class="sxs-lookup"><span data-stu-id="5e673-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="5e673-104">Los elementos XML de `x:XData` no deben ser tratados por los procesadores XAML como si formaran parte del espacio de nombres XAML predeterminado que actúa o cualquier otro espacio de nombres XAML.</span><span class="sxs-lookup"><span data-stu-id="5e673-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="5e673-105">`x:XData` puede contener XML con formato correcto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="5e673-105">`x:XData` can contain arbitrary well-formed XML.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="5e673-106">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="5e673-106">XAML Object Element Usage</span></span>

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a><span data-ttu-id="5e673-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="5e673-107">XAML Values</span></span>

|||
|-|-|
|`elementDataRoot`|<span data-ttu-id="5e673-108">Elemento raíz único de la isla de datos delimitada.</span><span class="sxs-lookup"><span data-stu-id="5e673-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="5e673-109">Para la mayoría de los consumidores eventuales, XML que no tiene una sola raíz se considera no válido.</span><span class="sxs-lookup"><span data-stu-id="5e673-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="5e673-110">En concreto, se requiere una sola raíz si `x:XData` se ha diseñado como origen de datos XML para WPF o muchas otras tecnologías que usan orígenes XML para el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="5e673-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|
|`[elementData]`|<span data-ttu-id="5e673-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5e673-111">Optional.</span></span> <span data-ttu-id="5e673-112">XML que representa los datos XML.</span><span class="sxs-lookup"><span data-stu-id="5e673-112">XML that represents the XML data.</span></span> <span data-ttu-id="5e673-113">Se puede incluir cualquier número de elementos como datos de elemento y los elementos anidados pueden estar contenidos en otros elementos; sin embargo, se aplican las reglas generales de XML.</span><span class="sxs-lookup"><span data-stu-id="5e673-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5e673-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e673-114">Remarks</span></span>

<span data-ttu-id="5e673-115">Los elementos XML dentro de un `x:XData` objeto pueden volver a declarar todos los espacios de nombres y prefijos posibles del que contiene XMLDOM dentro de los datos.</span><span class="sxs-lookup"><span data-stu-id="5e673-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>

<span data-ttu-id="5e673-116">El acceso mediante programación a los datos XML y el `x:XData` tipo XAML intrínseco es posible en los servicios XAML de .net a través de la <xref:System.Windows.Markup.XData> clase.</span><span class="sxs-lookup"><span data-stu-id="5e673-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="5e673-117">Notas de uso de WPF</span><span class="sxs-lookup"><span data-stu-id="5e673-117">WPF Usage Notes</span></span>

<span data-ttu-id="5e673-118">El `x:XData` objeto se utiliza principalmente como un objeto secundario de <xref:System.Windows.Data.XmlDataProvider> , o como alternativa, como el objeto secundario de la <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> propiedad (en XAML, normalmente se expresa en la sintaxis de elementos de propiedad).</span><span class="sxs-lookup"><span data-stu-id="5e673-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>

<span data-ttu-id="5e673-119">Normalmente, los datos deben volver a definir el espacio de nombres XML base dentro de la isla de datos para que sea un nuevo espacio de nombres XML predeterminado (establecido en una cadena vacía).</span><span class="sxs-lookup"><span data-stu-id="5e673-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="5e673-120">Esto es más fácil para las islas de datos simples porque las <xref:System.Windows.Data.Binding.XPath%2A> expresiones que se usan para hacer referencia y enlazar a los datos pueden evitar la inclusión de prefijos.</span><span class="sxs-lookup"><span data-stu-id="5e673-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="5e673-121">Las islas de datos más complejas pueden definir varios prefijos para los datos y usar un prefijo específico para el espacio de nombres XML en la raíz.</span><span class="sxs-lookup"><span data-stu-id="5e673-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="5e673-122">En este caso, todas <xref:System.Windows.Data.Binding.XPath%2A> las referencias a expresiones deben incluir el prefijo asignado por espacio de nombres adecuado.</span><span class="sxs-lookup"><span data-stu-id="5e673-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="5e673-123">Para obtener más información, vea [información general sobre el enlace de datos](../data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5e673-123">For more information, see [Data Binding Overview](../data/data-binding-overview.md).</span></span>

<span data-ttu-id="5e673-124">Técnicamente, `x:XData` se puede utilizar como contenido de cualquier propiedad de tipo <xref:System.Xml.Serialization.IXmlSerializable> .</span><span class="sxs-lookup"><span data-stu-id="5e673-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="5e673-125">Sin embargo, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> es la única implementación destacada.</span><span class="sxs-lookup"><span data-stu-id="5e673-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e673-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e673-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="5e673-127">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="5e673-127">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="5e673-128">Binding (extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="5e673-128">Binding Markup Extension</span></span>](/dotnet/desktop/wpf/advanced/binding-markup-extension)
