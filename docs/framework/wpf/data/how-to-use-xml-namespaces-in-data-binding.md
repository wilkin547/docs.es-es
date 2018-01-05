---
title: "Cómo: Usar espacios de nombres XML en el enlace de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f23e041a1e6b283cfe5308d6aef861f1fc757a7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="e91a6-102">Cómo: Usar espacios de nombres XML en el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="e91a6-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="e91a6-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e91a6-103">Example</span></span>  
 <span data-ttu-id="e91a6-104">En este ejemplo se muestra cómo controlar espacios de nombres especificados en el origen de enlace de [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e91a6-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>  
  
 <span data-ttu-id="e91a6-105">Si los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] tienen la definición de espacio de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] siguiente:</span><span class="sxs-lookup"><span data-stu-id="e91a6-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 <span data-ttu-id="e91a6-106">Puede usar el <xref:System.Windows.Data.XmlNamespaceMapping> elemento para asignar el espacio de nombres a un <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e91a6-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="e91a6-107">A continuación, puede usar el <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> para hacer referencia a la [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e91a6-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="e91a6-108">El <xref:System.Windows.Controls.ListBox> en este ejemplo se muestra la *título* y *DC: Date* de cada *elemento*.</span><span class="sxs-lookup"><span data-stu-id="e91a6-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 <span data-ttu-id="e91a6-109">Tenga en cuenta que la <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> especificar no tiene que coincidir con la utilizada en el [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] de origen; si cambia el prefijo en los [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] todavía funciona la asignación de origen.</span><span class="sxs-lookup"><span data-stu-id="e91a6-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>  
  
 <span data-ttu-id="e91a6-110">En este ejemplo concreto, la [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos proceden de un servicio web, pero la <xref:System.Windows.Data.XmlNamespaceMapping> elemento también funciona con en línea [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] o [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos en un archivo incrustado.</span><span class="sxs-lookup"><span data-stu-id="e91a6-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e91a6-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e91a6-111">See Also</span></span>  
 [<span data-ttu-id="e91a6-112">Enlazar a datos XML mediante XMLDataProvider y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="e91a6-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="e91a6-113">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="e91a6-113">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="e91a6-114">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="e91a6-114">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
