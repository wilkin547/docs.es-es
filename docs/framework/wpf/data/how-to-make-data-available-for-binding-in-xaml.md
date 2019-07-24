---
title: Procedimiento Hacer que los datos estén disponibles para el enlace en XAML
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 3487a160cc49ab6b779a20157668915c2da33900
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401495"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="16be0-102">Procedimiento Hacer que los datos estén disponibles para el enlace en XAML</span><span class="sxs-lookup"><span data-stu-id="16be0-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="16be0-103">En este tema se describen varias maneras en las que puede hacer que los [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]datos estén disponibles para el enlace en, en función de las necesidades de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="16be0-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16be0-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16be0-104">Example</span></span>  
 <span data-ttu-id="16be0-105">Si tiene un objeto Common Language Runtime (CLR) con el que le gustaría enlazar [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], una manera de hacer que el objeto esté disponible para el enlace es definirlo como un recurso y darle un. `x:Key`</span><span class="sxs-lookup"><span data-stu-id="16be0-105">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="16be0-106">En el ejemplo siguiente, tiene un `Person` objeto con una propiedad de cadena denominada. `PersonName`</span><span class="sxs-lookup"><span data-stu-id="16be0-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="16be0-107">El `Person` objeto (en la línea que se muestra resaltada que contiene el `<src>` elemento) se define `SDKSample`en el espacio de nombres denominado.</span><span class="sxs-lookup"><span data-stu-id="16be0-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="16be0-108">Después, puede enlazar <xref:System.Windows.Controls.TextBlock> el control al objeto de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], como se muestra en la línea resaltada que contiene el `<TextBlock>` elemento.</span><span class="sxs-lookup"><span data-stu-id="16be0-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span> 
  
 <span data-ttu-id="16be0-109">Como alternativa, puede usar la <xref:System.Windows.Data.ObjectDataProvider> clase, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16be0-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="16be0-110">El enlace se define de la misma manera, como se muestra en la línea `<TextBlock>` resaltada que contiene el elemento.</span><span class="sxs-lookup"><span data-stu-id="16be0-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="16be0-111">En este ejemplo concreto, el resultado es el mismo: tiene un <xref:System.Windows.Controls.TextBlock> con el contenido `Joe`de texto.</span><span class="sxs-lookup"><span data-stu-id="16be0-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="16be0-112">Sin embargo, <xref:System.Windows.Data.ObjectDataProvider> la clase proporciona funcionalidad como la capacidad de enlazar con el resultado de un método.</span><span class="sxs-lookup"><span data-stu-id="16be0-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="16be0-113">Puede optar por usar la <xref:System.Windows.Data.ObjectDataProvider> clase si necesita la funcionalidad que proporciona.</span><span class="sxs-lookup"><span data-stu-id="16be0-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="16be0-114">Sin embargo, si va a enlazar a un objeto que ya se ha creado, debe establecer `DataContext` en el código, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="16be0-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="16be0-115">Para obtener [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] acceso a los datos para <xref:System.Windows.Data.XmlDataProvider> el enlace mediante la clase, vea [enlazar a datos XML mediante XmlDataProvider y consultas XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="16be0-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="16be0-116">Para acceder [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] a los datos para el <xref:System.Windows.Data.ObjectDataProvider> enlace mediante la clase, vea [enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="16be0-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="16be0-117">Para obtener información acerca de muchas maneras de especificar los datos a los que se enlaza, vea [especificar el origen de enlace](how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="16be0-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="16be0-118">Para obtener información sobre los tipos de datos a los que puede enlazar o cómo implementar sus propios objetos Common Language Runtime (CLR) para el enlace, consulte [información general sobre orígenes de enlace](binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="16be0-118">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16be0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="16be0-119">See also</span></span>

- [<span data-ttu-id="16be0-120">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="16be0-120">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="16be0-121">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="16be0-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
