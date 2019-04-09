---
title: Filtrar Usar espacios de nombres XML en el enlace de datos
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 38bf6e8f88b0325193d49148cd6c33031f7b0a6d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149999"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="0ad40-102">Filtrar Usar espacios de nombres XML en el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="0ad40-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="0ad40-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ad40-103">Example</span></span>  
 <span data-ttu-id="0ad40-104">En este ejemplo se muestra cómo controlar espacios de nombres especificados en el origen de enlace de [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ad40-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>  
  
 <span data-ttu-id="0ad40-105">Si los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] tienen la definición de espacio de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ad40-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 <span data-ttu-id="0ad40-106">Puede usar el <xref:System.Windows.Data.XmlNamespaceMapping> elemento para asignar el espacio de nombres para un <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0ad40-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="0ad40-107">A continuación, puede usar el <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> para hacer referencia a la [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0ad40-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="0ad40-108">El <xref:System.Windows.Controls.ListBox> en este ejemplo muestra el *título* y *DC: Date* de cada *elemento*.</span><span class="sxs-lookup"><span data-stu-id="0ad40-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 <span data-ttu-id="0ad40-109">Tenga en cuenta que el <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> especificar no tiene que coincidir con la utilizada en el [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] de origen; si el prefijo cambia en el [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] origen de la asignación sigue funcionando.</span><span class="sxs-lookup"><span data-stu-id="0ad40-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>  
  
 <span data-ttu-id="0ad40-110">En este ejemplo concreto, el [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos proceden de un servicio web, pero la <xref:System.Windows.Data.XmlNamespaceMapping> elemento también funciona con inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] o [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos en un archivo incrustado.</span><span class="sxs-lookup"><span data-stu-id="0ad40-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad40-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ad40-111">See also</span></span>

- [<span data-ttu-id="0ad40-112">Enlazar a datos XML mediante XMLDataProvider y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="0ad40-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="0ad40-113">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="0ad40-113">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="0ad40-114">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="0ad40-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
