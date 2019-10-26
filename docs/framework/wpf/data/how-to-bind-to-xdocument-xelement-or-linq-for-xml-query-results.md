---
title: 'Cómo: Enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
ms.openlocfilehash: 070f67f30613d4522a48e08fd1c208fbe5887525
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920124"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a><span data-ttu-id="c93bd-102">Cómo: Enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement</span><span class="sxs-lookup"><span data-stu-id="c93bd-102">How to: Bind to XDocument, XElement, or LINQ for XML Query Results</span></span>

<span data-ttu-id="c93bd-103">En este ejemplo se muestra cómo enlazar datos XML a un <xref:System.Windows.Controls.ItemsControl> mediante <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="c93bd-103">This example demonstrates how to bind XML data to an <xref:System.Windows.Controls.ItemsControl> using <xref:System.Xml.Linq.XDocument>.</span></span>

## <a name="example"></a><span data-ttu-id="c93bd-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c93bd-104">Example</span></span>

<span data-ttu-id="c93bd-105">El código XAML siguiente define un <xref:System.Windows.Controls.ItemsControl> e incluye una plantilla de datos para los datos de tipo `Planet` en el espacio de nombres `http://planetsNS` XML.</span><span class="sxs-lookup"><span data-stu-id="c93bd-105">The following XAML code defines an <xref:System.Windows.Controls.ItemsControl> and includes a data template for data of type `Planet` in the `http://planetsNS` XML namespace.</span></span> <span data-ttu-id="c93bd-106">Un tipo de datos XML que ocupa un espacio de nombres debe incluir el espacio de nombres entre llaves y, si aparece donde podría aparecer una extensión de marcado XAML, debe preceder al espacio de nombres con una secuencia de escape de llaves.</span><span class="sxs-lookup"><span data-stu-id="c93bd-106">An XML data type that occupies a namespace must include the namespace in braces, and if it appears where a XAML markup extension could appear, it must precede the namespace with a brace escape sequence.</span></span> <span data-ttu-id="c93bd-107">Este código enlaza a las propiedades dinámicas que corresponden a los métodos <xref:System.Xml.Linq.XContainer.Element%2A> y <xref:System.Xml.Linq.XElement.Attribute%2A> de la clase <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="c93bd-107">This code binds to dynamic properties that correspond to the <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> methods of the <xref:System.Xml.Linq.XElement> class.</span></span> <span data-ttu-id="c93bd-108">Las propiedades dinámicas permiten a XAML enlazar a las propiedades dinámicas que comparten los nombres de los métodos.</span><span class="sxs-lookup"><span data-stu-id="c93bd-108">Dynamic properties enable XAML to bind to dynamic properties that share the names of methods.</span></span> <span data-ttu-id="c93bd-109">Para obtener más información, vea [LINQ to XML propiedades dinámicas](linq-to-xml-dynamic-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c93bd-109">To learn more, see [LINQ to XML dynamic properties](linq-to-xml-dynamic-properties.md).</span></span> <span data-ttu-id="c93bd-110">Tenga en cuenta cómo la declaración de espacio de nombres predeterminada para XML no se aplica a los nombres de atributo.</span><span class="sxs-lookup"><span data-stu-id="c93bd-110">Notice how the default namespace declaration for the XML does not apply to attribute names.</span></span>

[!code-xaml[XLinqExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]
[!code-xaml[XLinqExample#ItemsControl](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]

<span data-ttu-id="c93bd-111">En el C# código siguiente se llama a<xref:System.Xml.Linq.XDocument.Load%2A>y se establece el contexto de datos del panel de pila en todos los subelementos del elemento denominado`SolarSystemPlanets`en el espacio de nombres`http://planetsNS`XML.</span><span class="sxs-lookup"><span data-stu-id="c93bd-111">The following C# code calls <xref:System.Xml.Linq.XDocument.Load%2A> and sets the stack panel data context to all subelements of the element named `SolarSystemPlanets` in the `http://planetsNS` XML namespace.</span></span>

[!code-csharp[XLinqExample#LoadDCFromFile](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
[!code-vb[XLinqExample#LoadDCFromFile](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]

<span data-ttu-id="c93bd-112">Los datos XML se pueden almacenar como un recurso XAML mediante <xref:System.Windows.Data.ObjectDataProvider>.</span><span class="sxs-lookup"><span data-stu-id="c93bd-112">XML data can be stored as a XAML resource using <xref:System.Windows.Data.ObjectDataProvider>.</span></span> <span data-ttu-id="c93bd-113">Para obtener un ejemplo completo, vea el [código fuente L2DBForm. Xaml](l2dbform-xaml-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="c93bd-113">For a complete example, see  [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span> <span data-ttu-id="c93bd-114">En el ejemplo siguiente se muestra cómo el código puede establecer el contexto de datos en un recurso de objetos.</span><span class="sxs-lookup"><span data-stu-id="c93bd-114">The following sample shows how code can set the data context to an object resource.</span></span>

[!code-csharp[XLinqExample#LoadDCFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
[!code-vb[XLinqExample#LoadDCFromXAML](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]

<span data-ttu-id="c93bd-115">Las propiedades dinámicas que se asignan a <xref:System.Xml.Linq.XContainer.Element%2A> y <xref:System.Xml.Linq.XElement.Attribute%2A> proporcionan flexibilidad en XAML.</span><span class="sxs-lookup"><span data-stu-id="c93bd-115">The dynamic properties that map to <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> provide flexibility within XAML.</span></span> <span data-ttu-id="c93bd-116">El código también puede enlazar a los resultados de una consulta LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="c93bd-116">Your code can also bind to the results of a LINQ for XML query.</span></span> <span data-ttu-id="c93bd-117">Este ejemplo enlaza a los resultados de la consulta ordenados por un valor de elemento.</span><span class="sxs-lookup"><span data-stu-id="c93bd-117">This example binds to query results ordered by an element value.</span></span>

[!code-csharp[XLinqExample#BindToResults](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
[!code-vb[XLinqExample#BindToResults](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]

## <a name="see-also"></a><span data-ttu-id="c93bd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c93bd-118">See also</span></span>

- [<span data-ttu-id="c93bd-119">Información general sobre orígenes de enlaces</span><span class="sxs-lookup"><span data-stu-id="c93bd-119">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="c93bd-120">Información general de enlace de datos WPF con LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="c93bd-120">WPF Data Binding with LINQ to XML Overview</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="c93bd-121">Ejemplo de enlace de datos WPF mediante LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="c93bd-121">WPF Data Binding Using LINQ to XML Example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="c93bd-122">Propiedades dinámicas de LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="c93bd-122">LINQ to XML Dynamic Properties</span></span>](linq-to-xml-dynamic-properties.md)
