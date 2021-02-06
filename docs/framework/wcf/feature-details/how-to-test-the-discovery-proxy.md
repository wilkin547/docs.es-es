---
description: 'Más información acerca de cómo: probar el proxy de detección'
title: Procedimiento para probar el proxy de detección
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: 32360fd1f3724f2a557182ce2e11d346ba5c959d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643116"
---
# <a name="how-to-test-the-discovery-proxy"></a><span data-ttu-id="0267a-103">Procedimiento para probar el proxy de detección</span><span class="sxs-lookup"><span data-stu-id="0267a-103">How to: Test the Discovery Proxy</span></span>

<span data-ttu-id="0267a-104">Este es el cuarto de cuatro temas que indica cómo implementar un proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="0267a-104">This is the fourth of four topics that shows how to implement a discovery proxy.</span></span> <span data-ttu-id="0267a-105">En el tema anterior, [Cómo: implementar una aplicación cliente que utiliza el proxy de detección para buscar un servicio](client-app-discovery-proxy-to-find-a-service.md), ha implementado una aplicación cliente de WCF que usa el proxy de detección para buscar un servicio y, a continuación, llama al servicio.</span><span class="sxs-lookup"><span data-stu-id="0267a-105">In the previous topic, [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](client-app-discovery-proxy-to-find-a-service.md), you implemented a WCF client application that uses the discovery proxy to find a service and then calls the service.</span></span> <span data-ttu-id="0267a-106">Este tema describe cómo comprobar el proxy de detección, el servicio y el trabajo de la aplicación cliente según se espera.</span><span class="sxs-lookup"><span data-stu-id="0267a-106">This topic describes how to verify the discovery proxy, the service, and the client application work as expected.</span></span>  
  
### <a name="run-the-discovery-proxy"></a><span data-ttu-id="0267a-107">Ejecución del proxy de detección</span><span class="sxs-lookup"><span data-stu-id="0267a-107">Run the Discovery Proxy</span></span>  
  
1. <span data-ttu-id="0267a-108">Abra un símbolo del sistema como administrador.</span><span class="sxs-lookup"><span data-stu-id="0267a-108">Open a command prompt as an administrator.</span></span>  
  
2. <span data-ttu-id="0267a-109">Puede que aparezca un cuadro diálogo que dice: Firewall de Windows bloqueó algunas características de este programa.</span><span class="sxs-lookup"><span data-stu-id="0267a-109">You may see a dialog that says: Windows Firewall has blocked some features of this program.</span></span> <span data-ttu-id="0267a-110">Si ve este mensaje, haga clic en el botón **desbloquear** .</span><span class="sxs-lookup"><span data-stu-id="0267a-110">If you see this message, click the **Unblock** button.</span></span>  
  
3. <span data-ttu-id="0267a-111">Dentro del símbolo del sistema, ejecute el proxy de detección, DiscoveryProxy.exe.</span><span class="sxs-lookup"><span data-stu-id="0267a-111">Within the command prompt, run the discovery proxy, DiscoveryProxy.exe.</span></span>  
  
4. <span data-ttu-id="0267a-112">La aplicación debería mostrar el siguiente texto: `Proxy started. Hit Enter to exit`.</span><span class="sxs-lookup"><span data-stu-id="0267a-112">The application should display the following text: `Proxy started. Hit Enter to exit`.</span></span>  
  
### <a name="run-the-discoverable-service"></a><span data-ttu-id="0267a-113">Ejecución del servicio reconocible</span><span class="sxs-lookup"><span data-stu-id="0267a-113">Run the Discoverable Service</span></span>  
  
1. <span data-ttu-id="0267a-114">Abra un símbolo del sistema como administrador.</span><span class="sxs-lookup"><span data-stu-id="0267a-114">Open a command prompt as an administrator.</span></span>  
  
2. <span data-ttu-id="0267a-115">Desde el símbolo del sistema, ejecute el servicio reconocible Service.exe.</span><span class="sxs-lookup"><span data-stu-id="0267a-115">Within the command prompt, run the Service.exe discoverable service.</span></span>  
  
3. <span data-ttu-id="0267a-116">El DiscoveryProxy.exe debe mostrar el siguiente texto: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span><span class="sxs-lookup"><span data-stu-id="0267a-116">The DiscoveryProxy.exe should display the following text: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span></span>  
  
### <a name="run-the-client-application"></a><span data-ttu-id="0267a-117">Ejecución de la aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="0267a-117">Run the Client Application</span></span>  
  
1. <span data-ttu-id="0267a-118">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="0267a-118">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="0267a-119">Dentro del símbolo del sistema, ejecute la aplicación client.exe.</span><span class="sxs-lookup"><span data-stu-id="0267a-119">Within the command prompt, run the client.exe application.</span></span>  
  
3. <span data-ttu-id="0267a-120">Después de unos segundos, la aplicación cliente muestra el siguiente texto: Conectando con [servicio-extremo].</span><span class="sxs-lookup"><span data-stu-id="0267a-120">After a few seconds the client application displays the following text: Connecting to [Service-Endpoint].</span></span>  
  
4. <span data-ttu-id="0267a-121">A continuación, service.exe debería mostrar el siguiente texto: Solicitud de saludo recibida, responderé.</span><span class="sxs-lookup"><span data-stu-id="0267a-121">The service.exe should then display the following text: Greeting request received, I will respond.</span></span>  
  
5. <span data-ttu-id="0267a-122">A continuación, client.exe debería mostrar el siguiente texto: Hola, cliente.</span><span class="sxs-lookup"><span data-stu-id="0267a-122">The client.exe should then display the following text: Hello Client!</span></span>  
  
### <a name="shut-down-the-applications"></a><span data-ttu-id="0267a-123">Cierre de las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0267a-123">Shut Down the Applications</span></span>  
  
1. <span data-ttu-id="0267a-124">Cierre la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="0267a-124">Shut down the client application.</span></span>  
  
2. <span data-ttu-id="0267a-125">Cierre el servicio.</span><span class="sxs-lookup"><span data-stu-id="0267a-125">Shut down the service.</span></span> <span data-ttu-id="0267a-126">El proxy de detección muestra el siguiente texto: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span><span class="sxs-lookup"><span data-stu-id="0267a-126">The discovery proxy displays the following text: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span></span>  
  
3. <span data-ttu-id="0267a-127">Cierre el proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="0267a-127">Shut down the discovery proxy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0267a-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="0267a-128">See also</span></span>

- [<span data-ttu-id="0267a-129">Información general de Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="0267a-129">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)
- [<span data-ttu-id="0267a-130">Procedimiento para implementar un proxy de detección</span><span class="sxs-lookup"><span data-stu-id="0267a-130">How to: Implement a Discovery Proxy</span></span>](how-to-implement-a-discovery-proxy.md)
- [<span data-ttu-id="0267a-131">Procedimiento para implementar un servicio reconocible que se registra con el proxy de detección</span><span class="sxs-lookup"><span data-stu-id="0267a-131">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](discoverable-service-that-registers-with-the-discovery-proxy.md)
- [<span data-ttu-id="0267a-132">Procedimiento para implementar una aplicación cliente que usa el proxy de detección para buscar un servicio</span><span class="sxs-lookup"><span data-stu-id="0267a-132">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)
