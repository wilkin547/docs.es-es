---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 8f4dcf8f7d71cfa2ed9944822d7cce974e7f1979
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201569"
---
# \<backupList>

<span data-ttu-id="1ac36-101">Representa una sección de configuración para definir una lista auxiliar que enumera un conjunto de puntos de conexión que le gustaría que usara el servicio de enrutamiento en caso de que no se pueda alcanzar el punto de conexión primario.</span><span class="sxs-lookup"><span data-stu-id="1ac36-101">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="1ac36-102">Si el primer extremo en la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista.</span><span class="sxs-lookup"><span data-stu-id="1ac36-102">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="1ac36-103">De este modo, dispone de una forma rápida de agregar confiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar modelos complejos o dónde implementar todos sus servicios.</span><span class="sxs-lookup"><span data-stu-id="1ac36-103">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupList>**  
  
## <a name="syntax"></a><span data-ttu-id="1ac36-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ac36-104">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ac36-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1ac36-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1ac36-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1ac36-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ac36-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="1ac36-107">Attributes</span></span>  
  
|<span data-ttu-id="1ac36-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="1ac36-108">Attribute</span></span>|<span data-ttu-id="1ac36-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ac36-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ac36-110">name</span><span class="sxs-lookup"><span data-stu-id="1ac36-110">name</span></span>|<span data-ttu-id="1ac36-111">Cadena que especifica el nombre usado para identificar esta lista de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="1ac36-111">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ac36-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1ac36-112">Child Elements</span></span>  
  
|<span data-ttu-id="1ac36-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ac36-113">Element</span></span>|<span data-ttu-id="1ac36-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ac36-114">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="1ac36-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1ac36-115">Parent Elements</span></span>  
  
|<span data-ttu-id="1ac36-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ac36-116">Element</span></span>|<span data-ttu-id="1ac36-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ac36-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="1ac36-118">Lista de extremos auxiliares.</span><span class="sxs-lookup"><span data-stu-id="1ac36-118">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ac36-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1ac36-119">Remarks</span></span>  

 <span data-ttu-id="1ac36-120">Esta sección contiene una colección ordenada de extremos a los que se transmitirá un mensaje en caso de que se produzca una excepción de comunicaciones cuando se envíe al extremo primario.</span><span class="sxs-lookup"><span data-stu-id="1ac36-120">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="1ac36-121">Si un envío al punto de conexión principal que aparece en el `endpointName` atributo de [\<add>](add-of-entries.md) produce un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al primer punto de conexión en esta sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="1ac36-121">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="1ac36-122">Si esto también genera un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al siguiente mensaje que contiene esta sección hasta que el intento de envío se realice correctamente, que devuelva un error distinto de una excepción de comunicaciones o que todos los puntos de conexión de la colección hayan devuelto un error.</span><span class="sxs-lookup"><span data-stu-id="1ac36-122">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="1ac36-123">En el ejemplo siguiente, si un envío al punto de conexión principal denominado "Destination" devuelve una excepción de comunicación, el servicio intentará enviar el mensaje a "alternateServiceQueue".</span><span class="sxs-lookup"><span data-stu-id="1ac36-123">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="1ac36-124">Si este intento también devuelve una excepción de comunicación, el servicio de enrutamiento intentará enviar el mensaje al punto de conexión siguiente de la colección.</span><span class="sxs-lookup"><span data-stu-id="1ac36-124">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
  </filterTable>
</filterTables>
<backupLists>
  <backupList name="backupEndpointList">
    <add endpointName="backupServiceQueue" />
    <add endpointName="alternateServiceQueue" />
  </backupList>
</backupLists>
```  
  
## <a name="see-also"></a><span data-ttu-id="1ac36-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ac36-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
