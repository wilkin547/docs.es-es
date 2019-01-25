---
title: '&lt;backupLists&gt;'
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: fc9c697aff2e9c26c7922a0acaf5577b0dea2dc1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532375"
---
# <a name="ltbackuplistsgt"></a><span data-ttu-id="a8faa-102">&lt;backupLists&gt;</span><span class="sxs-lookup"><span data-stu-id="a8faa-102">&lt;backupLists&gt;</span></span>
<span data-ttu-id="a8faa-103">Representa una sección de configuración para definir un conjunto de servicios auxiliares usado en el control de errores.</span><span class="sxs-lookup"><span data-stu-id="a8faa-103">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="a8faa-104">Cada elemento secundario es una lista de reserva que enumera un conjunto de puntos de conexión que desea que el servicio de enrutamiento use en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="a8faa-104">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="a8faa-105">Si el primer punto de conexión en la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista.</span><span class="sxs-lookup"><span data-stu-id="a8faa-105">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="a8faa-106">De este modo, dispone de una forma rápida de agregar confiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar modelos complejos o dónde implementar todos sus servicios.</span><span class="sxs-lookup"><span data-stu-id="a8faa-106">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="a8faa-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a8faa-107">\<system.serviceModel></span></span>  
<span data-ttu-id="a8faa-108">\<routing></span><span class="sxs-lookup"><span data-stu-id="a8faa-108">\<routing></span></span>  
<span data-ttu-id="a8faa-109">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="a8faa-109">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8faa-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8faa-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8faa-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a8faa-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a8faa-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a8faa-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8faa-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="a8faa-113">Attributes</span></span>  
 <span data-ttu-id="a8faa-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a8faa-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a8faa-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a8faa-115">Child Elements</span></span>  
  
|<span data-ttu-id="a8faa-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="a8faa-116">Element</span></span>|<span data-ttu-id="a8faa-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8faa-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8faa-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="a8faa-118">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="a8faa-119">Contiene una lista de puntos de conexión que desea que el servicio de enrutamiento use en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="a8faa-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="a8faa-120">.</span><span class="sxs-lookup"><span data-stu-id="a8faa-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8faa-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a8faa-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a8faa-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="a8faa-122">Element</span></span>|<span data-ttu-id="a8faa-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8faa-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8faa-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="a8faa-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="a8faa-125">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, así como el enrutamiento de las tablas que definen los extremos de destino enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="a8faa-125">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8faa-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8faa-126">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
