---
title: "Cómo: Enlazar a un servicio web"
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
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d1b81949d6d91420c828564debd311af47dfdfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="701ef-102">Cómo: Enlazar a un servicio web</span><span class="sxs-lookup"><span data-stu-id="701ef-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="701ef-103">Este ejemplo muestra cómo enlazar a objetos devueltos por las llamadas de método de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="701ef-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="701ef-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="701ef-104">Example</span></span>  
 <span data-ttu-id="701ef-105">Este ejemplo se utiliza la [MSDN/TechNet Publishing System (MTPS) Content Service](http://go.microsoft.com/fwlink/?LinkId=95677) para recuperar la lista de idiomas admitidos por un documento especificado.</span><span class="sxs-lookup"><span data-stu-id="701ef-105">This example uses the [MSDN/TechNet Publishing System (MTPS) Content Service](http://go.microsoft.com/fwlink/?LinkId=95677) to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="701ef-106">Antes de llamar a un servicio Web, debe crear una referencia a él.</span><span class="sxs-lookup"><span data-stu-id="701ef-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="701ef-107">Para crear una referencia Web al servicio MTPS mediante [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="701ef-107">To create a Web reference to the MTPS service using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], follow the following steps:</span></span>  
  
1.  <span data-ttu-id="701ef-108">Abra el proyecto en [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].</span><span class="sxs-lookup"><span data-stu-id="701ef-108">Open your project in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="701ef-109">Desde el **proyecto** menú, haga clic en **Agregar referencia Web**.</span><span class="sxs-lookup"><span data-stu-id="701ef-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3.  <span data-ttu-id="701ef-110">En el cuadro de diálogo, establezca la **URL** a [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span><span class="sxs-lookup"><span data-stu-id="701ef-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4.  <span data-ttu-id="701ef-111">Presione **vaya** y, a continuación, **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="701ef-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="701ef-112">A continuación, llamar al método de servicio Web y establecer el <xref:System.Windows.FrameworkElement.DataContext%2A> del control adecuado o la ventana en el objeto devuelto.</span><span class="sxs-lookup"><span data-stu-id="701ef-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="701ef-113">El **GetContent** método del servicio MTPS toma una referencia a la **getContentRequest** objeto.</span><span class="sxs-lookup"><span data-stu-id="701ef-113">The **GetContent** method of the MTPS service takes a reference to the **getContentRequest** object.</span></span> <span data-ttu-id="701ef-114">Por lo tanto, en el ejemplo siguiente se establece primero un objeto de solicitud:</span><span class="sxs-lookup"><span data-stu-id="701ef-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="701ef-115">Después de la <xref:System.Windows.FrameworkElement.DataContext%2A> se ha establecido, se pueden crear enlaces a las propiedades del objeto que el <xref:System.Windows.FrameworkElement.DataContext%2A> se ha establecido en.</span><span class="sxs-lookup"><span data-stu-id="701ef-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="701ef-116">En este ejemplo, el <xref:System.Windows.FrameworkElement.DataContext%2A> está establecido en el **getContentResponse** objeto devuelto por la **GetContent** método.</span><span class="sxs-lookup"><span data-stu-id="701ef-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the **getContentResponse** object returned by the **GetContent** method.</span></span> <span data-ttu-id="701ef-117">En el ejemplo siguiente, la <xref:System.Windows.Controls.ItemsControl> enlaza a y muestra el **configuración regional** valores de **availableVersionsAndLocales** de **getContentResponse**.</span><span class="sxs-lookup"><span data-stu-id="701ef-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the **locale** values of **availableVersionsAndLocales** of **getContentResponse**.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="701ef-118">Para obtener información sobre la estructura de **getContentResponse**, consulte [Content Service documentation](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span><span class="sxs-lookup"><span data-stu-id="701ef-118">For information about the structure of **getContentResponse**, see [Content Service documentation](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="701ef-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="701ef-119">See Also</span></span>  
 [<span data-ttu-id="701ef-120">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="701ef-120">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="701ef-121">Información general sobre orígenes de enlaces</span><span class="sxs-lookup"><span data-stu-id="701ef-121">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="701ef-122">Hacer que los datos estén disponibles para el enlace en XAML</span><span class="sxs-lookup"><span data-stu-id="701ef-122">Make Data Available for Binding in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)
