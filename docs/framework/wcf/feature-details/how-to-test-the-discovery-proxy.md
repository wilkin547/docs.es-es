---
title: 'Cómo: Probar el proxy de detección'
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: 35edbd03e912ae2d9c491afb28dee1c4a3055d14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491227"
---
# <a name="how-to-test-the-discovery-proxy"></a><span data-ttu-id="7452b-102">Cómo: Probar el proxy de detección</span><span class="sxs-lookup"><span data-stu-id="7452b-102">How to: Test the Discovery Proxy</span></span>
<span data-ttu-id="7452b-103">Este es el cuarto de cuatro temas que indica cómo implementar un proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="7452b-103">This is the fourth of four topics that shows how to implement a discovery proxy.</span></span> <span data-ttu-id="7452b-104">En el tema anterior, [Cómo: implementar una aplicación de cliente que utiliza el Proxy de detección para buscar un servicio](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), implementa una aplicación de cliente WCF que usa el proxy de detección para buscar un servicio y, a continuación, llama al servicio.</span><span class="sxs-lookup"><span data-stu-id="7452b-104">In the previous topic, [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), you implemented a WCF client application that uses the discovery proxy to find a service and then calls the service.</span></span> <span data-ttu-id="7452b-105">Este tema describe cómo comprobar el proxy de detección, el servicio y el trabajo de la aplicación cliente según se espera.</span><span class="sxs-lookup"><span data-stu-id="7452b-105">This topic describes how to verify the discovery proxy, the service, and the client application work as expected.</span></span>  
  
### <a name="run-the-discovery-proxy"></a><span data-ttu-id="7452b-106">Ejecución del proxy de detección</span><span class="sxs-lookup"><span data-stu-id="7452b-106">Run the Discovery Proxy</span></span>  
  
1.  <span data-ttu-id="7452b-107">Abra un símbolo del sistema como administrador.</span><span class="sxs-lookup"><span data-stu-id="7452b-107">Open a command prompt as an administrator.</span></span>  
  
2.  <span data-ttu-id="7452b-108">Puede que aparezca un cuadro diálogo que dice: Firewall de Windows bloqueó algunas características de este programa.</span><span class="sxs-lookup"><span data-stu-id="7452b-108">You may see a dialog that says: Windows Firewall has blocked some features of this program.</span></span> <span data-ttu-id="7452b-109">Si ve este mensaje, haga clic en el **Unblock** botón.</span><span class="sxs-lookup"><span data-stu-id="7452b-109">If you see this message, click the **Unblock** button.</span></span>  
  
3.  <span data-ttu-id="7452b-110">Dentro del símbolo del sistema, ejecute el proxy de detección, DiscoveryProxy.exe.</span><span class="sxs-lookup"><span data-stu-id="7452b-110">Within the command prompt, run the discovery proxy, DiscoveryProxy.exe.</span></span>  
  
4.  <span data-ttu-id="7452b-111">La aplicación debería mostrar el siguiente texto: `Proxy started. Hit Enter to exit`.</span><span class="sxs-lookup"><span data-stu-id="7452b-111">The application should display the following text: `Proxy started. Hit Enter to exit`.</span></span>  
  
### <a name="run-the-discoverable-service"></a><span data-ttu-id="7452b-112">Ejecución del servicio reconocible</span><span class="sxs-lookup"><span data-stu-id="7452b-112">Run the Discoverable Service</span></span>  
  
1.  <span data-ttu-id="7452b-113">Abra un símbolo del sistema como administrador.</span><span class="sxs-lookup"><span data-stu-id="7452b-113">Open a command prompt as an administrator.</span></span>  
  
2.  <span data-ttu-id="7452b-114">Desde el símbolo del sistema, ejecute el servicio reconocible Service.exe.</span><span class="sxs-lookup"><span data-stu-id="7452b-114">Within the command prompt, run the Service.exe discoverable service.</span></span>  
  
3.  <span data-ttu-id="7452b-115">DiscoveryProxy.exe debería mostrar el siguiente texto: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span><span class="sxs-lookup"><span data-stu-id="7452b-115">The DiscoveryProxy.exe should display the following text: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span></span>  
  
### <a name="run-the-client-application"></a><span data-ttu-id="7452b-116">Ejecución de la aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="7452b-116">Run the Client Application</span></span>  
  
1.  <span data-ttu-id="7452b-117">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="7452b-117">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="7452b-118">Dentro del símbolo del sistema, ejecute la aplicación client.exe.</span><span class="sxs-lookup"><span data-stu-id="7452b-118">Within the command prompt, run the client.exe application.</span></span>  
  
3.  <span data-ttu-id="7452b-119">Después de unos segundos, la aplicación cliente muestra el siguiente texto: Conectando con [servicio-extremo].</span><span class="sxs-lookup"><span data-stu-id="7452b-119">After a few seconds the client application displays the following text: Connecting to [Service-Endpoint].</span></span>  
  
4.  <span data-ttu-id="7452b-120">A continuación, service.exe debería mostrar el siguiente texto: Solicitud de saludo recibida, responderé.</span><span class="sxs-lookup"><span data-stu-id="7452b-120">The service.exe should then display the following text: Greeting request received, I will respond.</span></span>  
  
5.  <span data-ttu-id="7452b-121">A continuación, client.exe debería mostrar el siguiente texto: Hola, cliente.</span><span class="sxs-lookup"><span data-stu-id="7452b-121">The client.exe should then display the following text: Hello Client!</span></span>  
  
### <a name="shut-down-the-applications"></a><span data-ttu-id="7452b-122">Cierre de las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="7452b-122">Shut Down the Applications</span></span>  
  
1.  <span data-ttu-id="7452b-123">Cierre la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="7452b-123">Shut down the client application.</span></span>  
  
2.  <span data-ttu-id="7452b-124">Cierre el servicio.</span><span class="sxs-lookup"><span data-stu-id="7452b-124">Shut down the service.</span></span> <span data-ttu-id="7452b-125">El proxy de detección muestra el siguiente texto: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span><span class="sxs-lookup"><span data-stu-id="7452b-125">The discovery proxy displays the following text: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span></span>  
  
3.  <span data-ttu-id="7452b-126">Cierre el proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="7452b-126">Shut down the discovery proxy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7452b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7452b-127">See Also</span></span>  
 [<span data-ttu-id="7452b-128">Información general de Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="7452b-128">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="7452b-129">Implementación de un proxy de detección</span><span class="sxs-lookup"><span data-stu-id="7452b-129">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 [<span data-ttu-id="7452b-130">Implementación de un servicio reconocible que se registra con el proxy de detección</span><span class="sxs-lookup"><span data-stu-id="7452b-130">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 [<span data-ttu-id="7452b-131">Implementación de una aplicación cliente que utiliza el proxy de detección para buscar un servicio</span><span class="sxs-lookup"><span data-stu-id="7452b-131">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
