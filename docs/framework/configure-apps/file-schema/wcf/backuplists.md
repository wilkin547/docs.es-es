---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5f2bb030d13389e15cb44f1ddff3b8168b4f2140
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850257"
---
# \<backupLists>
<span data-ttu-id="7ca52-101">Representa una sección de configuración para definir un conjunto de servicios auxiliares usado en el control de errores.</span><span class="sxs-lookup"><span data-stu-id="7ca52-101">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="7ca52-102">Cada elemento secundario es una lista auxiliar que enumera un conjunto de extremos que le gustaría que usara el servicio de enrutamiento en caso de que no se pudiera alcanzar el extremo primario.</span><span class="sxs-lookup"><span data-stu-id="7ca52-102">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="7ca52-103">Si el primer extremo en la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista.</span><span class="sxs-lookup"><span data-stu-id="7ca52-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="7ca52-104">De este modo, dispone de una forma rápida de agregar confiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar modelos complejos o dónde implementar todos sus servicios.</span><span class="sxs-lookup"><span data-stu-id="7ca52-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**  
  
## <a name="syntax"></a><span data-ttu-id="7ca52-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ca52-105">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ca52-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7ca52-106">Attributes and Elements</span></span>  
 <span data-ttu-id="7ca52-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7ca52-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ca52-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="7ca52-108">Attributes</span></span>  
 <span data-ttu-id="7ca52-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7ca52-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7ca52-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7ca52-110">Child Elements</span></span>  
  
|<span data-ttu-id="7ca52-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ca52-111">Element</span></span>|<span data-ttu-id="7ca52-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ca52-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)|<span data-ttu-id="7ca52-113">Contiene una lista de extremos que le gustaría que usara el servicio de enrutamiento en caso de que no se pudiera alcanzar el extremo primario.</span><span class="sxs-lookup"><span data-stu-id="7ca52-113">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="7ca52-114">.</span><span class="sxs-lookup"><span data-stu-id="7ca52-114">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7ca52-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7ca52-115">Parent Elements</span></span>  
  
|<span data-ttu-id="7ca52-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ca52-116">Element</span></span>|<span data-ttu-id="7ca52-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ca52-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="7ca52-118">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="7ca52-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ca52-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ca52-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
