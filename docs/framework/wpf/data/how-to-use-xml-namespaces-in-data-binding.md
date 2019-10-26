---
title: 'Cómo: Usar espacios de nombres XML en el enlace de datos'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 9d8ddc5445bac28c68cd6cc99acf3313613a8c7f
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919664"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="15817-102">Cómo: Usar espacios de nombres XML en el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="15817-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="15817-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15817-103">Example</span></span>
 <span data-ttu-id="15817-104">En este ejemplo se muestra cómo controlar espacios de nombres especificados en el origen de enlace de [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15817-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>

 <span data-ttu-id="15817-105">Si los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] tienen la definición de espacio de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] siguiente:</span><span class="sxs-lookup"><span data-stu-id="15817-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 <span data-ttu-id="15817-106">Puede usar el elemento <xref:System.Windows.Data.XmlNamespaceMapping> para asignar el espacio de nombres a un <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="15817-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="15817-107">Después, puede usar el <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> para hacer referencia al espacio de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15817-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="15817-108">En el <xref:System.Windows.Controls.ListBox> de este ejemplo se muestra el *título* y el *DC: fecha* de cada *elemento*.</span><span class="sxs-lookup"><span data-stu-id="15817-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 <span data-ttu-id="15817-109">Tenga en cuenta que el <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> que especifique no tiene que coincidir con el usado en el origen de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]; Si el prefijo cambia en el origen de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] la asignación sigue funcionando.</span><span class="sxs-lookup"><span data-stu-id="15817-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>

 <span data-ttu-id="15817-110">En este ejemplo concreto, los datos de la [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] proceden de un servicio Web, pero el elemento <xref:System.Windows.Data.XmlNamespaceMapping> también funciona con [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] en línea o datos de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] en un archivo incrustado.</span><span class="sxs-lookup"><span data-stu-id="15817-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>

## <a name="see-also"></a><span data-ttu-id="15817-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="15817-111">See also</span></span>

- [<span data-ttu-id="15817-112">Enlazar a datos XML mediante XMLDataProvider y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="15817-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="15817-113">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="15817-113">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="15817-114">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="15817-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
