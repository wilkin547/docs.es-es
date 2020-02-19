---
title: 'Cómo: Enlazar a un servicio web'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
ms.openlocfilehash: 3a3f6edc974448ddab9fe30e97bdc1130d3b97dc
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449977"
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="ce3dd-102">Cómo: Enlazar a un servicio web</span><span class="sxs-lookup"><span data-stu-id="ce3dd-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="ce3dd-103">En este ejemplo se muestra cómo enlazar a objetos devueltos por llamadas al método de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="ce3dd-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce3dd-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce3dd-104">Example</span></span>  
 <span data-ttu-id="ce3dd-105">En este ejemplo se usa el servicio de contenido de MSDN/TechNet Publishing System (MTPS) para recuperar la lista de idiomas admitidos por un documento especificado.</span><span class="sxs-lookup"><span data-stu-id="ce3dd-105">This example uses the MSDN/TechNet Publishing System (MTPS) Content Service to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="ce3dd-106">Antes de llamar a un servicio Web, debe crear una referencia a él.</span><span class="sxs-lookup"><span data-stu-id="ce3dd-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="ce3dd-107">Para crear una referencia Web al servicio MTPS mediante Visual Studio, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ce3dd-107">To create a Web reference to the MTPS service using Visual Studio, follow the following steps:</span></span>  
  
1. <span data-ttu-id="ce3dd-108">Abra el proyecto en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce3dd-108">Open your project in Visual Studio.</span></span>  
  
2. <span data-ttu-id="ce3dd-109">En el menú **proyecto** , haga clic en **Agregar referencia Web**.</span><span class="sxs-lookup"><span data-stu-id="ce3dd-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3. <span data-ttu-id="ce3dd-110">En el cuadro de diálogo, establezca la **dirección URL** en [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span><span class="sxs-lookup"><span data-stu-id="ce3dd-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4. <span data-ttu-id="ce3dd-111">Presione **Go** y luego **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="ce3dd-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="ce3dd-112">A continuación, llame al método de servicio Web y establezca el <xref:System.Windows.FrameworkElement.DataContext%2A> del control o de la ventana correspondiente en el objeto devuelto.</span><span class="sxs-lookup"><span data-stu-id="ce3dd-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="ce3dd-113">El método `GetContent` del servicio MTPS toma una referencia al objeto `getContentRequest`.</span><span class="sxs-lookup"><span data-stu-id="ce3dd-113">The `GetContent` method of the MTPS service takes a reference to the `getContentRequest` object.</span></span> <span data-ttu-id="ce3dd-114">Por lo tanto, en el ejemplo siguiente se configura primero un objeto de solicitud:</span><span class="sxs-lookup"><span data-stu-id="ce3dd-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="ce3dd-115">Una vez establecido el <xref:System.Windows.FrameworkElement.DataContext%2A>, puede crear enlaces a las propiedades del objeto en el que se ha establecido el <xref:System.Windows.FrameworkElement.DataContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce3dd-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="ce3dd-116">En este ejemplo, la <xref:System.Windows.FrameworkElement.DataContext%2A> se establece en el objeto `getContentResponse` devuelto por el método `GetContent`.</span><span class="sxs-lookup"><span data-stu-id="ce3dd-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the `getContentResponse` object returned by the `GetContent` method.</span></span> <span data-ttu-id="ce3dd-117">En el ejemplo siguiente, el <xref:System.Windows.Controls.ItemsControl> enlaza a y muestra los valores `locale` de `availableVersionsAndLocales` de `getContentResponse`.</span><span class="sxs-lookup"><span data-stu-id="ce3dd-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the `locale` values of `availableVersionsAndLocales` of `getContentResponse`.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="ce3dd-118">Para obtener información sobre la estructura de `getContentResponse`, consulte la [documentación del servicio de contenido](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span><span class="sxs-lookup"><span data-stu-id="ce3dd-118">For information about the structure of `getContentResponse`, see [Content Service documentation](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce3dd-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce3dd-119">See also</span></span>

- [<span data-ttu-id="ce3dd-120">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="ce3dd-120">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="ce3dd-121">Información general sobre orígenes de enlaces</span><span class="sxs-lookup"><span data-stu-id="ce3dd-121">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="ce3dd-122">Hacer que los datos estén disponibles para el enlace en XAML</span><span class="sxs-lookup"><span data-stu-id="ce3dd-122">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
