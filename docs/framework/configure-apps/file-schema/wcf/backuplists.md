---
description: 'Más información acerca de: <backupLists>'
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 9647c507f85eba6bfd001b34dbf617bc881d3f2e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749706"
---
# \<backupLists>

<span data-ttu-id="e4bd4-102">Representa una sección de configuración para definir un conjunto de servicios auxiliares usado en el control de errores.</span><span class="sxs-lookup"><span data-stu-id="e4bd4-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="e4bd4-103">Cada elemento secundario es una lista auxiliar que enumera un conjunto de extremos que le gustaría que usara el servicio de enrutamiento en caso de que no se pudiera alcanzar el extremo primario.</span><span class="sxs-lookup"><span data-stu-id="e4bd4-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="e4bd4-104">Si el primer extremo en la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista.</span><span class="sxs-lookup"><span data-stu-id="e4bd4-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="e4bd4-105">De este modo, dispone de una forma rápida de agregar confiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar modelos complejos o dónde implementar todos sus servicios.</span><span class="sxs-lookup"><span data-stu-id="e4bd4-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**  
  
## <a name="syntax"></a><span data-ttu-id="e4bd4-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4bd4-106">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4bd4-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e4bd4-107">Attributes and Elements</span></span>  

 <span data-ttu-id="e4bd4-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e4bd4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4bd4-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="e4bd4-109">Attributes</span></span>  

 <span data-ttu-id="e4bd4-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e4bd4-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e4bd4-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e4bd4-111">Child Elements</span></span>  
  
|<span data-ttu-id="e4bd4-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4bd4-112">Element</span></span>|<span data-ttu-id="e4bd4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4bd4-113">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)|<span data-ttu-id="e4bd4-114">Contiene una lista de extremos que le gustaría que usara el servicio de enrutamiento en caso de que no se pudiera alcanzar el extremo primario.</span><span class="sxs-lookup"><span data-stu-id="e4bd4-114">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="e4bd4-115">.</span><span class="sxs-lookup"><span data-stu-id="e4bd4-115">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e4bd4-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e4bd4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e4bd4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4bd4-117">Element</span></span>|<span data-ttu-id="e4bd4-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4bd4-118">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="e4bd4-119">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="e4bd4-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4bd4-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4bd4-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
