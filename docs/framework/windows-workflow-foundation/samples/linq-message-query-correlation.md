---
title: Correlación de consultas de mensajes LINQ
ms.date: 03/30/2017
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
ms.openlocfilehash: cd91a171f3242cfd7e8ac0404e24ac065919bcce
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094623"
---
# <a name="linq-message-query-correlation"></a><span data-ttu-id="5da7a-102">Correlación de consultas de mensajes LINQ</span><span class="sxs-lookup"><span data-stu-id="5da7a-102">LINQ Message Query Correlation</span></span>
<span data-ttu-id="5da7a-103">Este ejemplo muestra cómo realizar una correlación basada en contenidos mediante una implementación de <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizada en contraposición a <xref:System.ServiceModel.XPathMessageQuery> proporcionado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="5da7a-103">This sample demonstrates how to do content-based correlation using a custom <xref:System.ServiceModel.Dispatcher.MessageQuery> implementation as opposed to the system-provided <xref:System.ServiceModel.XPathMessageQuery>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="5da7a-104">Muestra</span><span class="sxs-lookup"><span data-stu-id="5da7a-104">Demonstrates</span></span>  
 <span data-ttu-id="5da7a-105"><xref:System.ServiceModel.Dispatcher.MessageQuery> personalizado, correlación basada en contenidos.</span><span class="sxs-lookup"><span data-stu-id="5da7a-105">Custom <xref:System.ServiceModel.Dispatcher.MessageQuery>, Content-Based Correlation.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="5da7a-106">Discusión</span><span class="sxs-lookup"><span data-stu-id="5da7a-106">Discussion</span></span>  
 <span data-ttu-id="5da7a-107">En este ejemplo se muestra cómo realizar una ampliación a partir de la clase base <xref:System.ServiceModel.Dispatcher.MessageQuery> para propósitos de correlación.</span><span class="sxs-lookup"><span data-stu-id="5da7a-107">This sample shows how to extend from the <xref:System.ServiceModel.Dispatcher.MessageQuery> base class for the purposes of correlation.</span></span> <span data-ttu-id="5da7a-108">La implementación personalizada, `LinqMessageQuery`, permite a los usuarios proporcionar un XName para encontrar dentro del mensaje utilizando XLinq.</span><span class="sxs-lookup"><span data-stu-id="5da7a-108">The custom implementation, `LinqMessageQuery`, allows users to provide an XName to find within the message using XLinq.</span></span> <span data-ttu-id="5da7a-109">Los datos recuperados por la consulta se utilizan para formar la clave de correlación para enviar los mensajes a la instancia de flujo de trabajo adecuada.</span><span class="sxs-lookup"><span data-stu-id="5da7a-109">The data retrieved by the query is used to form the correlation key to dispatch messages to the appropriate workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5da7a-110">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5da7a-110">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="5da7a-111">En este ejemplo se expone un servicio del flujo de trabajo mediante puntos de conexión HTTP.</span><span class="sxs-lookup"><span data-stu-id="5da7a-111">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="5da7a-112">Para ejecutar este ejemplo, se deben agregar las ACL de dirección URL adecuadas (consulte [configuración de http y https](../../wcf/feature-details/configuring-http-and-https.md) para obtener detalles), ya sea ejecutando Visual Studio como administrador o ejecutando el siguiente comando en un símbolo del sistema con privilegios elevados para agregar las ACL adecuadas.</span><span class="sxs-lookup"><span data-stu-id="5da7a-112">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](../../wcf/feature-details/configuring-http-and-https.md) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="5da7a-113">Asegúrese de que su dominio y su nombre de usuario se sustituyen.</span><span class="sxs-lookup"><span data-stu-id="5da7a-113">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. <span data-ttu-id="5da7a-114">Una vez agregadas las listas de control de acceso de dirección URL, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5da7a-114">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1. <span data-ttu-id="5da7a-115">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="5da7a-115">Build the solution.</span></span>  
  
    2. <span data-ttu-id="5da7a-116">Establezca varios proyectos de inicio haciendo clic con el botón derecho en la solución y seleccionando **establecer proyectos de inicio**.</span><span class="sxs-lookup"><span data-stu-id="5da7a-116">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="5da7a-117">Agregue el **servicio** y el **cliente** (en ese orden) como varios proyectos de inicio.</span><span class="sxs-lookup"><span data-stu-id="5da7a-117">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    3. <span data-ttu-id="5da7a-118">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5da7a-118">Run the application.</span></span> <span data-ttu-id="5da7a-119">La consola del cliente muestra un flujo de trabajo que envía un pedido y recibe el id. del pedido de compra y, a continuación, confirma el pedido.</span><span class="sxs-lookup"><span data-stu-id="5da7a-119">The client console shows a workflow  sending an order and receiving the purchase order id and then subsequently confirming the order.</span></span> <span data-ttu-id="5da7a-120">La ventana Servicio mostrará las solicitudes que se están procesando.</span><span class="sxs-lookup"><span data-stu-id="5da7a-120">The Service window will show the requests being processed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5da7a-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5da7a-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5da7a-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5da7a-122">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="5da7a-123">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5da7a-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5da7a-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="5da7a-124">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
