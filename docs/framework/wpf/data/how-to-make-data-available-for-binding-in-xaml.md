---
title: "Cómo: Hacer que los datos estén disponibles para el enlace en XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d734a7f17f8843ff284ac0854ac41d4a5b9f5584
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="f6b5f-102">Cómo: Hacer que los datos estén disponibles para el enlace en XAML</span><span class="sxs-lookup"><span data-stu-id="f6b5f-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="f6b5f-103">Este tema describen las distintas maneras en que puede hacer que datos disponibles para el enlace en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], en función de las necesidades de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="f6b5f-103">This topic discusses the different ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6b5f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f6b5f-104">Example</span></span>  
 <span data-ttu-id="f6b5f-105">Si tiene una [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] que desea enlazar a partir del objeto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], una manera de hacer que el objeto disponible para el enlace es para definir como un recurso y asígnele un `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="f6b5f-105">If you have a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="f6b5f-106">En el ejemplo siguiente, tendrá un `Person` objeto con una propiedad de cadena denominada `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="f6b5f-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="f6b5f-107">El `Person` objeto se define en el espacio de nombres denominado `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="f6b5f-107">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
  
 <span data-ttu-id="f6b5f-108">A continuación, puede enlazar al objeto en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f6b5f-108">You can then bind to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as shown in the following example.</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="f6b5f-109">Como alternativa, puede usar el <xref:System.Windows.Data.ObjectDataProvider> (clase), como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f6b5f-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example.</span></span>  
  
 [!code-xaml[SimpleBinding#ODPCP](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#odpcp)]  
  
 <span data-ttu-id="f6b5f-110">Definir el enlace de la misma manera:</span><span class="sxs-lookup"><span data-stu-id="f6b5f-110">You define the binding the same way:</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="f6b5f-111">En este ejemplo concreto, el resultado es el mismo: tiene un <xref:System.Windows.Controls.TextBlock> con el contenido de texto `Joe`.</span><span class="sxs-lookup"><span data-stu-id="f6b5f-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="f6b5f-112">Sin embargo, la <xref:System.Windows.Data.ObjectDataProvider> clase proporciona funcionalidad como la capacidad para enlazar al resultado de un método.</span><span class="sxs-lookup"><span data-stu-id="f6b5f-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="f6b5f-113">Puede usar el <xref:System.Windows.Data.ObjectDataProvider> si necesita la funcionalidad que proporciona la clase.</span><span class="sxs-lookup"><span data-stu-id="f6b5f-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="f6b5f-114">Sin embargo, si va a enlazar a un objeto que ya se ha creado, debe establecer el `DataContext` en el código, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f6b5f-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="f6b5f-115">Para tener acceso a [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos mediante un enlace el <xref:System.Windows.Data.XmlDataProvider> de clases, consulte [enlazar a datos XML mediante XMLDataProvider y consultas XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f6b5f-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="f6b5f-116">Para tener acceso a [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos mediante un enlace el <xref:System.Windows.Data.ObjectDataProvider> de clases, consulte [enlazar a XDocument, XElement o LINQ para resultados de consultas XML](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="f6b5f-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="f6b5f-117">Para obtener información sobre las distintas maneras en que puede especificar los datos que se va a enlazar a, vea [especificar el origen de enlace](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="f6b5f-117">For information about the different ways you can specify the data you are binding to, see [Specify the Binding Source](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="f6b5f-118">Para obtener información sobre cómo implementar su propia o qué tipos de datos puede enlazar a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objetos para el enlace, consulte [información general de los orígenes de enlace](../../../../docs/framework/wpf/data/binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f6b5f-118">For information about what types of data you can bind to or how to implement your own [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects for binding, see [Binding Sources Overview](../../../../docs/framework/wpf/data/binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b5f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6b5f-119">See Also</span></span>  
 [<span data-ttu-id="f6b5f-120">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="f6b5f-120">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="f6b5f-121">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="f6b5f-121">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
