---
title: 'Cómo: Usar espacios de nombres XML en el enlace de datos'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: f6e6e042fa5583fcf91bd15c524537490fb6670c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740578"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="3b283-102">Cómo: Usar espacios de nombres XML en el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="3b283-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="3b283-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b283-103">Example</span></span>
 <span data-ttu-id="3b283-104">En este ejemplo se muestra cómo controlar los espacios de nombres especificados en el origen de enlace XML.</span><span class="sxs-lookup"><span data-stu-id="3b283-104">This example shows how to handle namespaces specified in your XML binding source.</span></span>

 <span data-ttu-id="3b283-105">Si los datos XML tienen la siguiente definición de espacio de nombres XML:</span><span class="sxs-lookup"><span data-stu-id="3b283-105">If your XML data has the following XML namespace definition:</span></span>

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 <span data-ttu-id="3b283-106">Puede usar el elemento <xref:System.Windows.Data.XmlNamespaceMapping> para asignar el espacio de nombres a un <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3b283-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="3b283-107">Después, puede usar el <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> para hacer referencia al espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="3b283-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the XML namespace.</span></span> <span data-ttu-id="3b283-108">En el <xref:System.Windows.Controls.ListBox> de este ejemplo se muestra el *título* y el *DC: fecha* de cada *elemento*.</span><span class="sxs-lookup"><span data-stu-id="3b283-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 <span data-ttu-id="3b283-109">Tenga en cuenta que el <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> que especifique no tiene que coincidir con el utilizado en el origen XML; Si el prefijo cambia en el origen XML, la asignación sigue funcionando.</span><span class="sxs-lookup"><span data-stu-id="3b283-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the XML source; if the prefix changes in the XML source your mapping still works.</span></span>

 <span data-ttu-id="3b283-110">En este ejemplo concreto, los datos XML provienen de un servicio Web, pero el elemento <xref:System.Windows.Data.XmlNamespaceMapping> también funciona con datos XML o XML en línea en un archivo incrustado.</span><span class="sxs-lookup"><span data-stu-id="3b283-110">In this particular example, the XML data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline XML or XML data in an embedded file.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b283-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b283-111">See also</span></span>

- [<span data-ttu-id="3b283-112">Enlazar a datos XML mediante XMLDataProvider y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="3b283-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="3b283-113">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="3b283-113">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="3b283-114">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="3b283-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
