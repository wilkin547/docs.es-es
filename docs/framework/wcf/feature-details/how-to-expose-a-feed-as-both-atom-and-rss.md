---
description: 'Más información acerca de cómo: exponer una fuente como Atom y RSS'
title: Procedimiento para exponer una fuente como Atom y RSS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fe374932-67f5-487d-9325-f868812b92e4
ms.openlocfilehash: 5afe08b2c1d9fc687563e124061fe7fb59257180
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793784"
---
# <a name="how-to-expose-a-feed-as-both-atom-and-rss"></a><span data-ttu-id="da9cf-103">Procedimiento para exponer una fuente como Atom y RSS</span><span class="sxs-lookup"><span data-stu-id="da9cf-103">How to: Expose a Feed as Both Atom and RSS</span></span>

<span data-ttu-id="da9cf-104">Windows Communication Foundation (WCF) le permite crear un servicio que exponga una fuente de distribución.</span><span class="sxs-lookup"><span data-stu-id="da9cf-104">Windows Communication Foundation (WCF) allows you to create a service that exposes a syndication feed.</span></span> <span data-ttu-id="da9cf-105">En este tema se explica cómo crear un servicio de distribución que exponga una fuente de distribución mediante Atom 1.0 y RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="da9cf-105">This topic discusses how to create a syndication service that exposes a syndication feed using both Atom 1.0 and RSS 2.0.</span></span> <span data-ttu-id="da9cf-106">Este servicio expone un punto de conexión que puede devolver cualquiera de los dos formatos de distribución.</span><span class="sxs-lookup"><span data-stu-id="da9cf-106">This service exposes one endpoint that can return either syndication format.</span></span> <span data-ttu-id="da9cf-107">Para simplificar, el servicio usado en este ejemplo tiene host propio.</span><span class="sxs-lookup"><span data-stu-id="da9cf-107">For simplicity the service used in this sample is self hosted.</span></span> <span data-ttu-id="da9cf-108">En un entorno de producción un servicio de este tipo estaría hospedado en IIS o WAS.</span><span class="sxs-lookup"><span data-stu-id="da9cf-108">In a production environment a service of this type would be hosted under IIS or WAS.</span></span> <span data-ttu-id="da9cf-109">Para obtener más información acerca de las distintas opciones de hospedaje de WCF, vea [hospedaje](hosting.md).</span><span class="sxs-lookup"><span data-stu-id="da9cf-109">For more information about the different WCF hosting options, see [Hosting](hosting.md).</span></span>  
  
### <a name="to-create-a-basic-syndication-service"></a><span data-ttu-id="da9cf-110">Creación de un servicio de distribución básico</span><span class="sxs-lookup"><span data-stu-id="da9cf-110">To create a basic syndication service</span></span>  
  
1. <span data-ttu-id="da9cf-111">Defina un contrato de servicios utilizando una interfaz marcada con el atributo <xref:System.ServiceModel.Web.WebGetAttribute>.</span><span class="sxs-lookup"><span data-stu-id="da9cf-111">Define a service contract using an interface marked with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute.</span></span> <span data-ttu-id="da9cf-112">Cada operación que se expone como una fuente de distribución devuelve un objeto <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span><span class="sxs-lookup"><span data-stu-id="da9cf-112">Each operation that is exposed as a syndication feed returns a <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> object.</span></span> <span data-ttu-id="da9cf-113">Observe los parámetros de <xref:System.ServiceModel.Web.WebGetAttribute>.</span><span class="sxs-lookup"><span data-stu-id="da9cf-113">Note the parameters for the <xref:System.ServiceModel.Web.WebGetAttribute>.</span></span> <span data-ttu-id="da9cf-114">`UriTemplate` especifica la dirección URL usada para invocar esta operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="da9cf-114">`UriTemplate` specifies the URL used to invoke this service operation.</span></span> <span data-ttu-id="da9cf-115">La cadena de este parámetro contiene literales y una variable entre llaves ({*Format*}).</span><span class="sxs-lookup"><span data-stu-id="da9cf-115">The string for this parameter contains literals and a variable in braces ({*format*}).</span></span> <span data-ttu-id="da9cf-116">Esta variable corresponde al parámetro `format` de la operación del servicio.</span><span class="sxs-lookup"><span data-stu-id="da9cf-116">This variable corresponds to the service operation's `format` parameter.</span></span> <span data-ttu-id="da9cf-117">Para obtener más información, vea <xref:System.UriTemplate>.</span><span class="sxs-lookup"><span data-stu-id="da9cf-117">For more information, see <xref:System.UriTemplate>.</span></span> <span data-ttu-id="da9cf-118">`BodyStyle` afecta a cómo se escriben los mensajes que esta operación de servicio envía y recibe.</span><span class="sxs-lookup"><span data-stu-id="da9cf-118">`BodyStyle` affects how the messages that this service operation sends and receives are written.</span></span> <span data-ttu-id="da9cf-119"><xref:System.ServiceModel.Web.WebMessageBodyStyle.Bare> especifica que los datos enviados a y desde esta operación de servicio no están ajustados por los elementos XML definidos por la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="da9cf-119"><xref:System.ServiceModel.Web.WebMessageBodyStyle.Bare> specifies that the data sent to and from this service operation are not wrapped by infrastructure-defined XML elements.</span></span> <span data-ttu-id="da9cf-120">Para obtener más información, vea <xref:System.ServiceModel.Web.WebMessageBodyStyle>.</span><span class="sxs-lookup"><span data-stu-id="da9cf-120">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle>.</span></span>  
  
     [!code-csharp[htAtomRss#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#0)]
     [!code-vb[htAtomRss#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#0)]  
  
    > [!NOTE]
    > <span data-ttu-id="da9cf-121">Utilice el <xref:System.ServiceModel.ServiceKnownTypeAttribute> para especificar los tipos que devuelven las operaciones de servicio en esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="da9cf-121">Use the <xref:System.ServiceModel.ServiceKnownTypeAttribute> to specify the types that are returned by the service operations in this interface.</span></span>  
  
2. <span data-ttu-id="da9cf-122">Implemente el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="da9cf-122">Implement the service contract.</span></span>  
  
     [!code-csharp[htAtomRss#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#1)]
     [!code-vb[htAtomRss#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#1)]  
  
3. <span data-ttu-id="da9cf-123">Cree un objeto <xref:System.ServiceModel.Syndication.SyndicationFeed> y agregue un autor, categoría y descripción.</span><span class="sxs-lookup"><span data-stu-id="da9cf-123">Create a <xref:System.ServiceModel.Syndication.SyndicationFeed> object and add an author, category, and description.</span></span>  
  
     [!code-csharp[htAtomRss#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#2)]
     [!code-vb[htAtomRss#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#2)]  
  
4. <span data-ttu-id="da9cf-124">Cree varios objetos <xref:System.ServiceModel.Syndication.SyndicationItem>.</span><span class="sxs-lookup"><span data-stu-id="da9cf-124">Create several <xref:System.ServiceModel.Syndication.SyndicationItem> objects.</span></span>  
  
     [!code-csharp[htAtomRss#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#3)]
     [!code-vb[htAtomRss#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#3)]  
  
5. <span data-ttu-id="da9cf-125">Agregue los objetos <xref:System.ServiceModel.Syndication.SyndicationItem> a la fuente.</span><span class="sxs-lookup"><span data-stu-id="da9cf-125">Add the <xref:System.ServiceModel.Syndication.SyndicationItem> objects to the feed.</span></span>  
  
     [!code-csharp[htAtomRss#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#4)]
     [!code-vb[htAtomRss#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#4)]  
  
6. <span data-ttu-id="da9cf-126">Utilice el parámetro format para devolver el formato solicitado.</span><span class="sxs-lookup"><span data-stu-id="da9cf-126">Use the format parameter to return the requested format.</span></span>  
  
     [!code-csharp[htAtomRss#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#5)]
     [!code-vb[htAtomRss#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a><span data-ttu-id="da9cf-127">Para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="da9cf-127">To host the service</span></span>  
  
1. <span data-ttu-id="da9cf-128">Crear un objeto <xref:System.ServiceModel.Web.WebServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="da9cf-128">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span> <span data-ttu-id="da9cf-129">La clase <xref:System.ServiceModel.Web.WebServiceHost> agrega automáticamente un punto de conexión en la dirección base del servicio, salvo que se especifique uno en el código o en la configuración.</span><span class="sxs-lookup"><span data-stu-id="da9cf-129">The <xref:System.ServiceModel.Web.WebServiceHost> class automatically adds an endpoint at the service's base address unless one is specified in code or configuration.</span></span> <span data-ttu-id="da9cf-130">En este ejemplo, no se especifica ningún punto de conexión, por lo que se expone el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="da9cf-130">In this sample, no endpoints are specified so the default endpoint is exposed.</span></span>  
  
     [!code-csharp[htAtomRss#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#6)]
     [!code-vb[htAtomRss#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#6)]  
  
2. <span data-ttu-id="da9cf-131">Abra el host de servicio, cargue la fuente desde el servicio, muestre la fuente y espere a que el usuario presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="da9cf-131">Open the service host, load the feed from the service, display the feed, and wait for the user to press ENTER.</span></span>  
  
     [!code-csharp[htAtomRss#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#8)]
     [!code-vb[htAtomRss#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a><span data-ttu-id="da9cf-132">Llamar a GetBlog mediante HTTP GET</span><span class="sxs-lookup"><span data-stu-id="da9cf-132">To call GetBlog with an HTTP GET</span></span>  
  
1. <span data-ttu-id="da9cf-133">Abra Internet Explorer, escriba la siguiente dirección URL y presione ENTRAR: `http://localhost:8000/BlogService/GetBlog` .</span><span class="sxs-lookup"><span data-stu-id="da9cf-133">Open Internet Explorer, type the following URL, and press ENTER: `http://localhost:8000/BlogService/GetBlog`.</span></span>
  
     <span data-ttu-id="da9cf-134">La dirección URL contiene la dirección base del servicio ( `http://localhost:8000/BlogService` ), la dirección relativa del punto de conexión y la operación de servicio que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="da9cf-134">The URL contains the base address of the service (`http://localhost:8000/BlogService`), the relative address of the endpoint, and the service operation to call.</span></span>  
  
### <a name="to-call-getblog-from-code"></a><span data-ttu-id="da9cf-135">Llamar a GetBlog() mediante código</span><span class="sxs-lookup"><span data-stu-id="da9cf-135">To call GetBlog() from code</span></span>  
  
1. <span data-ttu-id="da9cf-136">Cree un <xref:System.Xml.XmlReader> con la dirección base y el método al que está llamando.</span><span class="sxs-lookup"><span data-stu-id="da9cf-136">Create an <xref:System.Xml.XmlReader> with the base address and the method you are calling.</span></span>  
  
     [!code-csharp[htAtomRss#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#9)]
     [!code-vb[htAtomRss#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#9)]  
  
2. <span data-ttu-id="da9cf-137">Llame al método estático <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29>, pasando el <xref:System.Xml.XmlReader> que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="da9cf-137">Call the static <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> method, passing in the <xref:System.Xml.XmlReader> you just created.</span></span>  
  
     [!code-csharp[htAtomRss#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#10)]
     [!code-vb[htAtomRss#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#10)]  
  
     <span data-ttu-id="da9cf-138">Esto invoca la operación de servicio y rellena una nueva <xref:System.ServiceModel.Syndication.SyndicationFeed> con el formateador devuelto desde la operación del servicio.</span><span class="sxs-lookup"><span data-stu-id="da9cf-138">This invokes the service operation and populates a new <xref:System.ServiceModel.Syndication.SyndicationFeed> with the formatter returned from the service operation.</span></span>  
  
3. <span data-ttu-id="da9cf-139">Obtenga acceso al objeto de fuente.</span><span class="sxs-lookup"><span data-stu-id="da9cf-139">Access the feed object.</span></span>  
  
     [!code-csharp[htAtomRss#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#11)]
     [!code-vb[htAtomRss#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="da9cf-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da9cf-140">Example</span></span>  

 <span data-ttu-id="da9cf-141">A continuación, se muestra una lista de código completa para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="da9cf-141">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[htAtomRss#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#12)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="da9cf-142">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="da9cf-142">Compiling the Code</span></span>  

 <span data-ttu-id="da9cf-143">Al compilar el código anterior, haga referencia a System.ServiceModel.dll y System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="da9cf-143">When compiling the preceding code, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da9cf-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="da9cf-144">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
