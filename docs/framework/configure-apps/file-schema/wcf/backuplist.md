---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: b0a6c604b5741c1355c35fca510cd10544dab9f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704432"
---
# <a name="backuplist"></a><span data-ttu-id="f3cb8-101">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="f3cb8-101">\<backupList></span></span>
<span data-ttu-id="f3cb8-102">Representa una sección de configuración para definir una lista de reserva que enumera un conjunto de puntos de conexión que desea que el servicio de enrutamiento use en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="f3cb8-102">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="f3cb8-103">Si el primer extremo en la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista.</span><span class="sxs-lookup"><span data-stu-id="f3cb8-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="f3cb8-104">De este modo, dispone de una forma rápida de agregar confiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar modelos complejos o dónde implementar todos sus servicios.</span><span class="sxs-lookup"><span data-stu-id="f3cb8-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="f3cb8-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f3cb8-105">\<system.serviceModel></span></span>  
<span data-ttu-id="f3cb8-106">\<routing></span><span class="sxs-lookup"><span data-stu-id="f3cb8-106">\<routing></span></span>  
<span data-ttu-id="f3cb8-107">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="f3cb8-107">\<backupLists></span></span>  
<span data-ttu-id="f3cb8-108">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="f3cb8-108">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3cb8-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3cb8-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3cb8-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f3cb8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f3cb8-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f3cb8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3cb8-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="f3cb8-112">Attributes</span></span>  
  
|<span data-ttu-id="f3cb8-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="f3cb8-113">Attribute</span></span>|<span data-ttu-id="f3cb8-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3cb8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3cb8-115">name</span><span class="sxs-lookup"><span data-stu-id="f3cb8-115">name</span></span>|<span data-ttu-id="f3cb8-116">Cadena que especifica el nombre usado para identificar esta lista de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="f3cb8-116">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3cb8-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f3cb8-117">Child Elements</span></span>  
  
|<span data-ttu-id="f3cb8-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3cb8-118">Element</span></span>|<span data-ttu-id="f3cb8-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3cb8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3cb8-120">\<filter></span><span class="sxs-lookup"><span data-stu-id="f3cb8-120">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="f3cb8-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f3cb8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f3cb8-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3cb8-122">Element</span></span>|<span data-ttu-id="f3cb8-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3cb8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3cb8-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="f3cb8-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="f3cb8-125">Lista de extremos auxiliares.</span><span class="sxs-lookup"><span data-stu-id="f3cb8-125">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3cb8-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3cb8-126">Remarks</span></span>  
 <span data-ttu-id="f3cb8-127">Esta sección contiene una colección ordenada de extremos a los que se transmitirá un mensaje en caso de que se produzca una excepción de comunicaciones cuando se envíe al extremo primario.</span><span class="sxs-lookup"><span data-stu-id="f3cb8-127">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="f3cb8-128">Si un envío al punto de conexión principal aparece en el `endpointName` atributo de [ \<Agregar >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) produce un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al primer punto de conexión en este sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="f3cb8-128">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="f3cb8-129">Si esto también genera un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al siguiente mensaje que contiene esta sección hasta que el intento de envío se realice correctamente, que devuelva un error distinto de una excepción de comunicaciones o que todos los puntos de conexión de la colección hayan devuelto un error.</span><span class="sxs-lookup"><span data-stu-id="f3cb8-129">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="f3cb8-130">En el siguiente ejemplo, si un envío al punto de conexión primario denominado "Destino" devuelve una excepción de comunicaciones, el servicio intentará enviar el mensaje a "alternateServiceQueue".</span><span class="sxs-lookup"><span data-stu-id="f3cb8-130">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="f3cb8-131">Si este intento también devuelve una excepción de comunicación, el servicio de enrutamiento intentará enviar el mensaje al punto de conexión siguiente de la colección.</span><span class="sxs-lookup"><span data-stu-id="f3cb8-131">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f3cb8-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3cb8-132">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
