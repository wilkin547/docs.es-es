---
title: Aislamiento de red para aplicaciones de la Tienda Windows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: ba7e480f50d3a339648229f17152eb28b28ec159
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="network-isolation-for-windows-store-apps"></a><span data-ttu-id="34101-102">Aislamiento de red para aplicaciones de la Tienda Windows</span><span class="sxs-lookup"><span data-stu-id="34101-102">Network Isolation for Windows Store Apps</span></span>
<span data-ttu-id="34101-103">Es posible usar las clases de los espacios de nombres <xref:System.Net>, <xref:System.Net.Http> y <xref:System.Net.Http.Headers> para desarrollar aplicaciones de la Tienda Windows o aplicaciones de escritorio.</span><span class="sxs-lookup"><span data-stu-id="34101-103">Classes in the <xref:System.Net>,  <xref:System.Net.Http>, and <xref:System.Net.Http.Headers> namespaces can be used to develop Windows Store  apps  or desktop apps.</span></span> <span data-ttu-id="34101-104">Cuando se usan en una aplicación de la Tienda Windows, las clases de estos espacios de nombres se ven afectadas por el aislamiento de red, que forma parte del modelo de seguridad para las aplicaciones usado por [!INCLUDE[win8](../../../includes/win8-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34101-104">When used in a Windows Store app, classes in these namespaces are affected by network isolation, part of the application security model used by the [!INCLUDE[win8](../../../includes/win8-md.md)].</span></span> <span data-ttu-id="34101-105">Las funcionalidades de red correspondientes deben estar habilitadas en el manifiesto de la aplicación de la Tienda Windows para que el sistema permita el acceso a la red.</span><span class="sxs-lookup"><span data-stu-id="34101-105">The appropriate network capabilities must be enabled in the app manifest for a Windows Store app for the system to allow network access.</span></span>  
  
## <a name="checklist-for-network-isolation"></a><span data-ttu-id="34101-106">Lista de comprobación para el aislamiento de red</span><span class="sxs-lookup"><span data-stu-id="34101-106">Checklist for Network Isolation</span></span>  
 <span data-ttu-id="34101-107">Use esta lista de comprobación para asegurarse de que el aislamiento de red está configurado para la aplicación de la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="34101-107">Use this checklist to be sure that network isolation is configured for your Windows Store app.</span></span>  
  
1.  <span data-ttu-id="34101-108">Determine la dirección de las solicitudes de acceso a la red que necesita la aplicación.</span><span class="sxs-lookup"><span data-stu-id="34101-108">Determine the direction of network access requests needed by the app.</span></span> <span data-ttu-id="34101-109">Puede tratarse de solicitudes salientes iniciadas por el cliente, solicitudes entrantes no solicitadas o una combinación de ambos tipos de solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="34101-109">This can be either outbound client-initiated requests or inbound unsolicited requests or it could be a combination of both of these network request types.</span></span>  
  
2.  <span data-ttu-id="34101-110">Determine el tipo de recursos de red con los que se comunicará la aplicación.</span><span class="sxs-lookup"><span data-stu-id="34101-110">Determine the type of network resources that that app will communicate with.</span></span> <span data-ttu-id="34101-111">Una aplicación podría tener que comunicarse con recursos de confianza en una red doméstica o de trabajo.</span><span class="sxs-lookup"><span data-stu-id="34101-111">An app may need to communicate with trusted resources on a Home or Work network.</span></span> <span data-ttu-id="34101-112">Una aplicación podría tener que comunicarse con recursos de Internet.</span><span class="sxs-lookup"><span data-stu-id="34101-112">An app might need to communicate with resources on the Internet.</span></span> <span data-ttu-id="34101-113">Una aplicación podría necesitar tener acceso a ambos tipos de recursos de red.</span><span class="sxs-lookup"><span data-stu-id="34101-113">An app might need access to both types of network resources.</span></span>  
  
3.  <span data-ttu-id="34101-114">Configure las funcionalidades mínimas necesarias de aislamiento de red en el manifiesto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="34101-114">Configure the minimum-required networking isolation capabilities in the app manifest.</span></span>  
  
4.  <span data-ttu-id="34101-115">Implemente y ejecute la aplicación para probarla mediante las herramientas de aislamiento de red proporcionadas para la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="34101-115">Deploy and run your app to test it using the network isolation tools provided for troubleshooting.</span></span>  
  
 <span data-ttu-id="34101-116">Para obtener más información sobre cómo configurar las funcionalidades de red y las herramientas de aislamiento que se usan para la solución de problemas de aislamiento de red, vea [Cómo configurar las funcionalidades de aislamiento de red](http://go.microsoft.com/fwlink/?LinkID=228265) en la documentación para desarrolladores de [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34101-116">For more detailed information on how to configure network capabilities and isolation tools used for troubleshooting network isolation, see [How to configure network isolation capabilities](http://go.microsoft.com/fwlink/?LinkID=228265) in the [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] developer documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34101-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="34101-117">See Also</span></span>  
 [<span data-ttu-id="34101-118">Conectarse a un servicio web</span><span class="sxs-lookup"><span data-stu-id="34101-118">Connecting to a web service</span></span>](http://go.microsoft.com/fwlink/?LinkID=245696)  
 [<span data-ttu-id="34101-119">Directrices y lista de comprobación para el aislamiento de red</span><span class="sxs-lookup"><span data-stu-id="34101-119">Guidelines and checklist for network isolation</span></span>](http://go.microsoft.com/fwlink/?LinkID=228265)  
 [<span data-ttu-id="34101-120">Inicio rápido: Conectarse usando HttpClient</span><span class="sxs-lookup"><span data-stu-id="34101-120">Quickstart: Connecting using HttpClient</span></span>](http://go.microsoft.com/fwlink/?LinkId=245697)  
 [<span data-ttu-id="34101-121">Cómo utilizar controladores de HttpClient</span><span class="sxs-lookup"><span data-stu-id="34101-121">How to use HttpClient handlers</span></span>](http://go.microsoft.com/fwlink/?LinkId=245699)  
 [<span data-ttu-id="34101-122">Cómo proteger las conexiones de HttpClient</span><span class="sxs-lookup"><span data-stu-id="34101-122">How to secure HttpClient connections</span></span>](http://go.microsoft.com/fwlink/?LinkId=245698)  
 [<span data-ttu-id="34101-123">Ejemplo de HttpClient</span><span class="sxs-lookup"><span data-stu-id="34101-123">HttpClient Sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=242550)
