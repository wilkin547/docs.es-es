---
title: Procedimiento para crear una fuente Atom básica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6e0cacc1-9b11-4665-adb7-577a62626fd6
ms.openlocfilehash: 0317e7b42f589b31f5c77b89d26cb46815f13054
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599053"
---
# <a name="how-to-create-a-basic-atom-feed"></a><span data-ttu-id="d9163-102">Procedimiento para crear una fuente Atom básica</span><span class="sxs-lookup"><span data-stu-id="d9163-102">How to: Create a Basic Atom Feed</span></span>
<span data-ttu-id="d9163-103">Windows Communication Foundation (WCF) le permite crear un servicio que exponga una fuente de distribución.</span><span class="sxs-lookup"><span data-stu-id="d9163-103">Windows Communication Foundation (WCF) allows you to create a service that exposes a syndication feed.</span></span> <span data-ttu-id="d9163-104">En este tema se discute cómo crear un servicio de distribución que exponga una fuente de distribución Atom.</span><span class="sxs-lookup"><span data-stu-id="d9163-104">This topic discusses how to create a syndication service that exposes an Atom syndication feed.</span></span>  
  
### <a name="to-create-a-basic-syndication-service"></a><span data-ttu-id="d9163-105">Creación de un servicio de distribución básico</span><span class="sxs-lookup"><span data-stu-id="d9163-105">To create a basic syndication service</span></span>  
  
1. <span data-ttu-id="d9163-106">Defina un contrato de servicios utilizando una interfaz marcada con el atributo <xref:System.ServiceModel.Web.WebGetAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d9163-106">Define a service contract using an interface marked with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute.</span></span> <span data-ttu-id="d9163-107">Cada operación que se expone como una fuente de distribución debería devolver un objeto <xref:System.ServiceModel.Syndication.Atom10FeedFormatter>.</span><span class="sxs-lookup"><span data-stu-id="d9163-107">Each operation that is exposed as a syndication feed should return a <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> object.</span></span>  
  
     [!code-csharp[htAtomBasic#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#0)]
     [!code-vb[htAtomBasic#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#0)]  
  
    > [!NOTE]
    > <span data-ttu-id="d9163-108">Todas las operaciones de servicio que apliquen el <xref:System.ServiceModel.Web.WebGetAttribute> se asignan a solicitudes HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="d9163-108">All service operations that apply the <xref:System.ServiceModel.Web.WebGetAttribute> are mapped to HTTP GET requests.</span></span> <span data-ttu-id="d9163-109">Para asignar su operación a un método HTTP diferente, utilice en su lugar <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d9163-109">To map your operation to a different HTTP method, use the <xref:System.ServiceModel.Web.WebInvokeAttribute> instead.</span></span> <span data-ttu-id="d9163-110">Para obtener más información, consulte [Cómo: crear un servicio http Web de WCF básico](how-to-create-a-basic-wcf-web-http-service.md).</span><span class="sxs-lookup"><span data-stu-id="d9163-110">For more information, see [How to: Create a Basic WCF Web HTTP Service](how-to-create-a-basic-wcf-web-http-service.md).</span></span>  
  
2. <span data-ttu-id="d9163-111">Implemente el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="d9163-111">Implement the service contract.</span></span>  
  
     [!code-csharp[htAtomBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#1)]
     [!code-vb[htAtomBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#1)]  
  
3. <span data-ttu-id="d9163-112">Cree un objeto <xref:System.ServiceModel.Syndication.SyndicationFeed> y agregue un autor, categoría y descripción.</span><span class="sxs-lookup"><span data-stu-id="d9163-112">Create a <xref:System.ServiceModel.Syndication.SyndicationFeed> object and add an author, category, and description.</span></span>  
  
     [!code-csharp[htAtomBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#2)]
     [!code-vb[htAtomBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#2)]  
  
4. <span data-ttu-id="d9163-113">Cree varios objetos <xref:System.ServiceModel.Syndication.SyndicationItem>.</span><span class="sxs-lookup"><span data-stu-id="d9163-113">Create several <xref:System.ServiceModel.Syndication.SyndicationItem> objects.</span></span>  
  
     [!code-csharp[htAtomBasic#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#3)]
     [!code-vb[htAtomBasic#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#3)]  
  
5. <span data-ttu-id="d9163-114">Agregue los objetos <xref:System.ServiceModel.Syndication.SyndicationItem> a la fuente.</span><span class="sxs-lookup"><span data-stu-id="d9163-114">Add the <xref:System.ServiceModel.Syndication.SyndicationItem> objects to the feed.</span></span>  
  
     [!code-csharp[htAtomBasic#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#4)]
     [!code-vb[htAtomBasic#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#4)]  
  
6. <span data-ttu-id="d9163-115">Devuelva la fuente.</span><span class="sxs-lookup"><span data-stu-id="d9163-115">Return the feed.</span></span>  
  
     [!code-csharp[htAtomBasic#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#5)]
     [!code-vb[htAtomBasic#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a><span data-ttu-id="d9163-116">Para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="d9163-116">To host the service</span></span>  
  
1. <span data-ttu-id="d9163-117">Crear un objeto <xref:System.ServiceModel.Web.WebServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d9163-117">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span>  
  
     [!code-csharp[htAtomBasic#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#6)]
     [!code-vb[htAtomBasic#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#6)]  
  
2. <span data-ttu-id="d9163-118">Abra el host de servicio, cargue la fuente desde el servicio, muestre la fuente y espere a que el usuario presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="d9163-118">Open the service host, load the feed from the service, display the feed, and wait for the user to press ENTER.</span></span>  
  
     [!code-csharp[htAtomBasic#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#8)]
     [!code-vb[htAtomBasic#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a><span data-ttu-id="d9163-119">Realización de llamadas a GetBlog() mediante HTTP GET</span><span class="sxs-lookup"><span data-stu-id="d9163-119">To call GetBlog() with an HTTP GET</span></span>  
  
1. <span data-ttu-id="d9163-120">Abra Internet Explorer, escriba la siguiente dirección URL y presione ENTRAR:`http://localhost:8000/BlogService/GetBlog`</span><span class="sxs-lookup"><span data-stu-id="d9163-120">Open Internet Explorer, type the following URL, and press ENTER: `http://localhost:8000/BlogService/GetBlog`</span></span>  
  
     <span data-ttu-id="d9163-121">La dirección URL contiene la dirección base del servicio ( `http://localhost:8000/BlogService` ), la dirección relativa del punto de conexión y la operación de servicio que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="d9163-121">The URL contains the base address of the service (`http://localhost:8000/BlogService`), the relative address of the endpoint, and the service operation to call.</span></span>  
  
### <a name="to-call-getblog-from-code"></a><span data-ttu-id="d9163-122">Llamar a GetBlog() mediante código</span><span class="sxs-lookup"><span data-stu-id="d9163-122">To call GetBlog() from code</span></span>  
  
1. <span data-ttu-id="d9163-123">Cree un <xref:System.Xml.XmlReader> con la dirección base y el método al que está llamando.</span><span class="sxs-lookup"><span data-stu-id="d9163-123">Create a <xref:System.Xml.XmlReader> with the base address and the method you are calling.</span></span>  
  
     [!code-csharp[htAtomBasic#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#9)]
     [!code-vb[htAtomBasic#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#9)]  
  
2. <span data-ttu-id="d9163-124">Llame al método estático <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29>, pasando el <xref:System.Xml.XmlReader> que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="d9163-124">Call the static <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> method, passing in the <xref:System.Xml.XmlReader> you just created.</span></span>  
  
     [!code-csharp[htAtomBasic#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#10)]
     [!code-vb[htAtomBasic#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#10)]  
  
     <span data-ttu-id="d9163-125">Esto invoca la operación de servicio y rellena una nueva <xref:System.ServiceModel.Syndication.SyndicationFeed> con el formateador devuelto desde la operación del servicio.</span><span class="sxs-lookup"><span data-stu-id="d9163-125">This invokes the service operation and populates a new <xref:System.ServiceModel.Syndication.SyndicationFeed> with the formatter returned from the service operation.</span></span>  
  
3. <span data-ttu-id="d9163-126">Obtenga acceso al objeto de fuente.</span><span class="sxs-lookup"><span data-stu-id="d9163-126">Access the feed object.</span></span>  
  
     [!code-csharp[htAtomBasic#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#11)]
     [!code-vb[htAtomBasic#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="d9163-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9163-127">Example</span></span>  
 <span data-ttu-id="d9163-128">A continuación, se muestra una lista de código completa para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d9163-128">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[htAtomBasic#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#12)]
 [!code-vb[htAtomBasic#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#12)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d9163-129">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d9163-129">Compiling the Code</span></span>  
 <span data-ttu-id="d9163-130">Al compilar el código anterior, haga referencia a System.ServiceModel.dll y System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="d9163-130">When compiling the preceding code, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9163-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9163-131">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
