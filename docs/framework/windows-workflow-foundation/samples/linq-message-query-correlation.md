---
title: Correlación de consultas de mensajes LINQ
ms.date: 03/30/2017
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
ms.openlocfilehash: 507001b165efdcbe7c1e27a07749dbe2eafb468f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182805"
---
# <a name="linq-message-query-correlation"></a><span data-ttu-id="58e71-102">Correlación de consultas de mensajes LINQ</span><span class="sxs-lookup"><span data-stu-id="58e71-102">LINQ Message Query Correlation</span></span>
<span data-ttu-id="58e71-103">Este ejemplo muestra cómo realizar una correlación basada en contenidos mediante una implementación de <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizada en contraposición a <xref:System.ServiceModel.XPathMessageQuery> proporcionado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="58e71-103">This sample demonstrates how to do content-based correlation using a custom <xref:System.ServiceModel.Dispatcher.MessageQuery> implementation as opposed to the system-provided <xref:System.ServiceModel.XPathMessageQuery>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="58e71-104">Muestra</span><span class="sxs-lookup"><span data-stu-id="58e71-104">Demonstrates</span></span>  
 <span data-ttu-id="58e71-105"><xref:System.ServiceModel.Dispatcher.MessageQuery> personalizado, correlación basada en contenidos.</span><span class="sxs-lookup"><span data-stu-id="58e71-105">Custom <xref:System.ServiceModel.Dispatcher.MessageQuery>, Content-Based Correlation.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="58e71-106">Discusión</span><span class="sxs-lookup"><span data-stu-id="58e71-106">Discussion</span></span>  
 <span data-ttu-id="58e71-107">En este ejemplo se muestra cómo realizar una ampliación a partir de la clase base <xref:System.ServiceModel.Dispatcher.MessageQuery> para propósitos de correlación.</span><span class="sxs-lookup"><span data-stu-id="58e71-107">This sample shows how to extend from the <xref:System.ServiceModel.Dispatcher.MessageQuery> base class for the purposes of correlation.</span></span> <span data-ttu-id="58e71-108">La implementación personalizada, `LinqMessageQuery`, permite a los usuarios proporcionar un XName para encontrar dentro del mensaje utilizando XLinq.</span><span class="sxs-lookup"><span data-stu-id="58e71-108">The custom implementation, `LinqMessageQuery`, allows users to provide an XName to find within the message using XLinq.</span></span> <span data-ttu-id="58e71-109">Los datos recuperados por la consulta se utilizan para formar la clave de correlación para enviar los mensajes a la instancia de flujo de trabajo adecuada.</span><span class="sxs-lookup"><span data-stu-id="58e71-109">The data retrieved by the query is used to form the correlation key to dispatch messages to the appropriate workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="58e71-110">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="58e71-110">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="58e71-111">En este ejemplo se expone un servicio del flujo de trabajo mediante puntos de conexión HTTP.</span><span class="sxs-lookup"><span data-stu-id="58e71-111">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="58e71-112">Para ejecutar este ejemplo, se deben agregar las ACL de dirección URL adecuadas (consulte Configuración de [HTTP y HTTPS](../../wcf/feature-details/configuring-http-and-https.md) para obtener más información), ya sea ejecutando Visual Studio como administrador o ejecutando el siguiente comando en un símbolo del sistema con privilegios elevados para agregar las ACL adecuadas.</span><span class="sxs-lookup"><span data-stu-id="58e71-112">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](../../wcf/feature-details/configuring-http-and-https.md) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="58e71-113">Asegúrese de que su dominio y su nombre de usuario se sustituyen.</span><span class="sxs-lookup"><span data-stu-id="58e71-113">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. <span data-ttu-id="58e71-114">Una vez agregadas las listas de control de acceso de dirección URL, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="58e71-114">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1. <span data-ttu-id="58e71-115">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="58e71-115">Build the solution.</span></span>  
  
    2. <span data-ttu-id="58e71-116">Establezca varios proyectos de inicio haciendo clic con el botón derecho en la solución y seleccionando **Establecer proyectos**de inicio .</span><span class="sxs-lookup"><span data-stu-id="58e71-116">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="58e71-117">Agregue **Servicio** y **Cliente** (en ese orden) como varios proyectos de inicio.</span><span class="sxs-lookup"><span data-stu-id="58e71-117">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    3. <span data-ttu-id="58e71-118">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="58e71-118">Run the application.</span></span> <span data-ttu-id="58e71-119">La consola del cliente muestra un flujo de trabajo que envía un pedido y recibe el id. del pedido de compra y, a continuación, confirma el pedido.</span><span class="sxs-lookup"><span data-stu-id="58e71-119">The client console shows a workflow  sending an order and receiving the purchase order id and then subsequently confirming the order.</span></span> <span data-ttu-id="58e71-120">La ventana Servicio mostrará las solicitudes que se están procesando.</span><span class="sxs-lookup"><span data-stu-id="58e71-120">The Service window will show the requests being processed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="58e71-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="58e71-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="58e71-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="58e71-122">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="58e71-123">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="58e71-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="58e71-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="58e71-124">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
