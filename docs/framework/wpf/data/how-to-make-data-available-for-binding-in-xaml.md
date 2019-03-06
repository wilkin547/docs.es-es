---
title: Filtrar Hacer que los datos estén disponibles para el enlace en XAML
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 1f024ddd0be023f77408e3106bc0a4465d068074
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358293"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="6a3a1-102">Filtrar Hacer que los datos estén disponibles para el enlace en XAML</span><span class="sxs-lookup"><span data-stu-id="6a3a1-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="6a3a1-103">Este tema describen varias maneras de hacer que datos disponibles para enlace en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], según las necesidades de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="6a3a1-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a3a1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a3a1-104">Example</span></span>  
 <span data-ttu-id="6a3a1-105">Si tiene un [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] desea enlazar a partir de objetos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], una forma que puede que el objeto esté disponible de enlace consiste en definir como un recurso y asígnele un `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="6a3a1-105">If you have a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="6a3a1-106">En el ejemplo siguiente, tendrá un `Person` objeto con una propiedad de cadena denominada `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="6a3a1-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="6a3a1-107">El `Person` objeto (en la línea que se muestra resaltada que contiene el `<src>` elemento) se define en el espacio de nombres denominado `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="6a3a1-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="6a3a1-108">A continuación, puede enlazar el <xref:System.Windows.Controls.TextBlock> control en el objeto en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], como el resaltado de línea que contiene el `<TextBlock>` elemento muestra.</span><span class="sxs-lookup"><span data-stu-id="6a3a1-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span> 
  
 <span data-ttu-id="6a3a1-109">Como alternativa, puede usar el <xref:System.Windows.Data.ObjectDataProvider> (clase), como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6a3a1-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="6a3a1-110">Definir el enlace de la misma manera, como la línea resaltada que contiene el `<TextBlock>` muestra de elemento.</span><span class="sxs-lookup"><span data-stu-id="6a3a1-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="6a3a1-111">En este ejemplo concreto, el resultado es el mismo: tiene un <xref:System.Windows.Controls.TextBlock> con el contenido de texto `Joe`.</span><span class="sxs-lookup"><span data-stu-id="6a3a1-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="6a3a1-112">Sin embargo, la <xref:System.Windows.Data.ObjectDataProvider> clase proporciona funcionalidad como la capacidad para enlazar con el resultado de un método.</span><span class="sxs-lookup"><span data-stu-id="6a3a1-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="6a3a1-113">Puede usar el <xref:System.Windows.Data.ObjectDataProvider> si necesita la funcionalidad que proporciona la clase.</span><span class="sxs-lookup"><span data-stu-id="6a3a1-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="6a3a1-114">Sin embargo, si va a enlazar a un objeto que ya se ha creado, debe establecer el `DataContext` en código, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6a3a1-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="6a3a1-115">Para tener acceso a [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos para el enlace mediante la <xref:System.Windows.Data.XmlDataProvider> de clases, vea [enlazar a datos XML mediante XMLDataProvider y consultas XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="6a3a1-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="6a3a1-116">Para tener acceso a [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos para el enlace mediante la <xref:System.Windows.Data.ObjectDataProvider> de clases, vea [enlazar a XElement, XDocument o LINQ para resultados de consultas XML](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="6a3a1-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="6a3a1-117">Para obtener información acerca de muchas maneras puede especificar los datos que se va a enlazar a, vea [especificar el origen de enlace](how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="6a3a1-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="6a3a1-118">Para obtener información sobre qué tipos de datos se puede enlazar o cómo implementar su propio [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objetos para el enlace, consulte [Binding Sources Overview](binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6a3a1-118">For information about what types of data you can bind to or how to implement your own [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a3a1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a3a1-119">See also</span></span>
- [<span data-ttu-id="6a3a1-120">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="6a3a1-120">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="6a3a1-121">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="6a3a1-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
