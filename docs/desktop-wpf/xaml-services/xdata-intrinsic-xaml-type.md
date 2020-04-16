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
ms.openlocfilehash: b7f0954158988db107feb4a6c51ba81d5db11dcb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432795"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="70fb3-102">x:XData (Tipo XAML intrínseco)</span><span class="sxs-lookup"><span data-stu-id="70fb3-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="70fb3-103">Habilita la colocación de islas de datos XML dentro de una producción XAML.</span><span class="sxs-lookup"><span data-stu-id="70fb3-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="70fb3-104">Los procesadores XAML no `x:XData` deben tratar los elementos XML dentro como si formaran parte del espacio de nombres XAML predeterminado que actúa o de cualquier otro espacio de nombres XAML.</span><span class="sxs-lookup"><span data-stu-id="70fb3-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="70fb3-105">`x:XData`puede contener XML arbitrario bien formado.</span><span class="sxs-lookup"><span data-stu-id="70fb3-105">`x:XData` can contain arbitrary well-formed XML.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="70fb3-106">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="70fb3-106">XAML Object Element Usage</span></span>

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a><span data-ttu-id="70fb3-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="70fb3-107">XAML Values</span></span>

|||
|-|-|
|`elementDataRoot`|<span data-ttu-id="70fb3-108">El único elemento raíz de la isla de datos cerrada.</span><span class="sxs-lookup"><span data-stu-id="70fb3-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="70fb3-109">Para la mayoría de los consumidores eventuales, XML que no tiene una sola raíz se considera no válido.</span><span class="sxs-lookup"><span data-stu-id="70fb3-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="70fb3-110">En concreto, se requiere una `x:XData` única raíz si está pensado como un origen de datos XML para WPFo o muchas otras tecnologías que usan orígenes XML para el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="70fb3-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|
|`[elementData]`|<span data-ttu-id="70fb3-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="70fb3-111">Optional.</span></span> <span data-ttu-id="70fb3-112">XML que representa los datos XML.</span><span class="sxs-lookup"><span data-stu-id="70fb3-112">XML that represents the XML data.</span></span> <span data-ttu-id="70fb3-113">Cualquier número de elementos puede contenerse como datos de elemento y los elementos anidados pueden estar contenidos en otros elementos; sin embargo, se aplican las reglas generales de XML.</span><span class="sxs-lookup"><span data-stu-id="70fb3-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|

## <a name="remarks"></a><span data-ttu-id="70fb3-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="70fb3-114">Remarks</span></span>

<span data-ttu-id="70fb3-115">Los elementos `x:XData` XML dentro de un objeto pueden volver a declarar todos los espacios de nombres y prefijos posibles del XMLDOM contenedor dentro de los datos.</span><span class="sxs-lookup"><span data-stu-id="70fb3-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>

<span data-ttu-id="70fb3-116">El acceso mediante programación `x:XData` a los datos XML y el <xref:System.Windows.Markup.XData> tipo XAML intrínseco es posible en los servicios XAML de .NET a través de la clase.</span><span class="sxs-lookup"><span data-stu-id="70fb3-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="70fb3-117">Notas de uso de WPF</span><span class="sxs-lookup"><span data-stu-id="70fb3-117">WPF Usage Notes</span></span>

<span data-ttu-id="70fb3-118">El `x:XData` objeto se utiliza principalmente como <xref:System.Windows.Data.XmlDataProvider>un objeto secundario de un <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> , o alternativamente, como el objeto secundario de la propiedad (en XAML, esto se expresa normalmente en la sintaxis del elemento de propiedad).</span><span class="sxs-lookup"><span data-stu-id="70fb3-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>

<span data-ttu-id="70fb3-119">Normalmente, los datos deben redefinir el espacio de nombres XML base dentro de la isla de datos para que sea un nuevo espacio de nombres XML predeterminado (establecido en una cadena vacía).</span><span class="sxs-lookup"><span data-stu-id="70fb3-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="70fb3-120">Esto es más fácil para <xref:System.Windows.Data.Binding.XPath%2A> las islas de datos simples porque las expresiones que se utilizan para hacer referencia y enlazar a los datos pueden evitar la inclusión de prefijos.</span><span class="sxs-lookup"><span data-stu-id="70fb3-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="70fb3-121">Las islas de datos más complejas podrían definir varios prefijos para los datos y usar un prefijo específico para el espacio de nombres XML en la raíz.</span><span class="sxs-lookup"><span data-stu-id="70fb3-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="70fb3-122">En este caso, todas las <xref:System.Windows.Data.Binding.XPath%2A> referencias de expresión deben incluir el prefijo asignado al espacio de nombres adecuado.</span><span class="sxs-lookup"><span data-stu-id="70fb3-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="70fb3-123">Para obtener más información, vea [Información general sobre el enlace](../data/data-binding-overview.md)de datos .</span><span class="sxs-lookup"><span data-stu-id="70fb3-123">For more information, see [Data Binding Overview](../data/data-binding-overview.md).</span></span>

<span data-ttu-id="70fb3-124">Técnicamente, `x:XData` se puede utilizar como el <xref:System.Xml.Serialization.IXmlSerializable>contenido de cualquier propiedad de tipo .</span><span class="sxs-lookup"><span data-stu-id="70fb3-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="70fb3-125">Sin <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> embargo, es la única implementación prominente.</span><span class="sxs-lookup"><span data-stu-id="70fb3-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="70fb3-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="70fb3-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="70fb3-127">Descripción general del enlace de datos</span><span class="sxs-lookup"><span data-stu-id="70fb3-127">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="70fb3-128">Enlazar extensión de marcado</span><span class="sxs-lookup"><span data-stu-id="70fb3-128">Binding Markup Extension</span></span>](../../framework/wpf/advanced/binding-markup-extension.md)
