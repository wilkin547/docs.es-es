---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 6ac7ff19c76097cb54e7b77db21cad50b49513c0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55280753"
---
# <a name="backuplists"></a><span data-ttu-id="4c268-101">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="4c268-101">\<backupLists></span></span>
<span data-ttu-id="4c268-102">Representa una sección de configuración para definir un conjunto de servicios auxiliares usado en el control de errores.</span><span class="sxs-lookup"><span data-stu-id="4c268-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="4c268-103">Cada elemento secundario es una lista de reserva que enumera un conjunto de puntos de conexión que desea que el servicio de enrutamiento use en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="4c268-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="4c268-104">Si el primer punto de conexión en la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista.</span><span class="sxs-lookup"><span data-stu-id="4c268-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="4c268-105">De este modo, dispone de una forma rápida de agregar confiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar modelos complejos o dónde implementar todos sus servicios.</span><span class="sxs-lookup"><span data-stu-id="4c268-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="4c268-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4c268-106">\<system.serviceModel></span></span>  
<span data-ttu-id="4c268-107">\<routing></span><span class="sxs-lookup"><span data-stu-id="4c268-107">\<routing></span></span>  
<span data-ttu-id="4c268-108">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="4c268-108">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c268-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c268-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c268-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4c268-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4c268-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4c268-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c268-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="4c268-112">Attributes</span></span>  
 <span data-ttu-id="4c268-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4c268-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4c268-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4c268-114">Child Elements</span></span>  
  
|<span data-ttu-id="4c268-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="4c268-115">Element</span></span>|<span data-ttu-id="4c268-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c268-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c268-117">\<filter></span><span class="sxs-lookup"><span data-stu-id="4c268-117">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="4c268-118">Contiene una lista de puntos de conexión que desea que el servicio de enrutamiento use en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="4c268-118">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="4c268-119">.</span><span class="sxs-lookup"><span data-stu-id="4c268-119">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c268-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4c268-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4c268-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="4c268-121">Element</span></span>|<span data-ttu-id="4c268-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c268-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c268-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="4c268-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="4c268-124">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, así como el enrutamiento de las tablas que definen los extremos de destino enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="4c268-124">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c268-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c268-125">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
