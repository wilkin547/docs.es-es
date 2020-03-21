---
title: 'Cómo: Hacer que los datos estén disponibles para el enlace en XAML'
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 91e89dbf36024c31f4afcd9b6d956944baf13576
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174191"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="cb4f5-102">Cómo: Hacer que los datos estén disponibles para el enlace en XAML</span><span class="sxs-lookup"><span data-stu-id="cb4f5-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="cb4f5-103">En este tema se describen varias formas [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]de hacer que los datos estén disponibles para el enlace en , en función de las necesidades de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb4f5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb4f5-104">Example</span></span>  
 <span data-ttu-id="cb4f5-105">Si tiene un objeto de Common Language Runtime (CLR) al que desea enlazar desde [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], una forma de hacer `x:Key`que el objeto esté disponible para el enlace es definirlo como un recurso y darle un archivo .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-105">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="cb4f5-106">En el ejemplo siguiente, `Person` tiene un objeto `PersonName`con una propiedad string denominada .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="cb4f5-107">El `Person` objeto (en la línea mostrada `<src>` resaltada que contiene `SDKSample`el elemento) se define en el espacio de nombres denominado .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="cb4f5-108">A continuación, <xref:System.Windows.Controls.TextBlock> puede enlazar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]control al objeto en `<TextBlock>` , como se muestra la línea resaltada que contiene el elemento.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span>
  
 <span data-ttu-id="cb4f5-109">Como alternativa, puede <xref:System.Windows.Data.ObjectDataProvider> utilizar la clase, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cb4f5-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="cb4f5-110">El enlace se define de la misma manera, `<TextBlock>` como se muestra la línea resaltada que contiene el elemento.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="cb4f5-111">En este ejemplo en particular, el resultado <xref:System.Windows.Controls.TextBlock> es el `Joe`mismo: tiene a con el contenido de texto .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="cb4f5-112">Sin <xref:System.Windows.Data.ObjectDataProvider> embargo, la clase proporciona funcionalidad como la capacidad de enlazar al resultado de un método.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="cb4f5-113">Puede elegir utilizar <xref:System.Windows.Data.ObjectDataProvider> la clase si necesita la funcionalidad que proporciona.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="cb4f5-114">Sin embargo, si va a enlazar a un objeto `DataContext` que ya se ha creado, debe establecer el código in, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="cb4f5-115">Para obtener acceso a <xref:System.Windows.Data.XmlDataProvider> los datos XML para enlazar mediante la clase, vea [Enlazar a datos XML mediante un XMLDataProvider y consultas XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="cb4f5-115">To access XML data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="cb4f5-116">Para obtener acceso a <xref:System.Windows.Data.ObjectDataProvider> los datos XML para enlazar mediante la clase, vea [Enlazar a XDocument, XElement o LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="cb4f5-116">To access XML data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="cb4f5-117">Para obtener información sobre muchas formas de especificar los datos a los que está enlazando, vea [Especificar el origen](how-to-specify-the-binding-source.md)de enlace .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="cb4f5-118">Para obtener información sobre los tipos de datos a los que puede enlazar o cómo implementar sus propios objetos de Common Language Runtime (CLR) para el enlace, vea [Información general sobre orígenes](binding-sources-overview.md)de enlace .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-118">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb4f5-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb4f5-119">See also</span></span>

- [<span data-ttu-id="cb4f5-120">Descripción general del enlace de datos</span><span class="sxs-lookup"><span data-stu-id="cb4f5-120">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="cb4f5-121">Temas de información</span><span class="sxs-lookup"><span data-stu-id="cb4f5-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
