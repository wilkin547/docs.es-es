---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: d5feab6cb374f98e683cf15f797de4f478e23131
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919924"
---
# <a name="backuplist"></a><span data-ttu-id="418d8-101">\<> backupList</span><span class="sxs-lookup"><span data-stu-id="418d8-101">\<backupList></span></span>
<span data-ttu-id="418d8-102">Representa una sección de configuración para definir una lista de copia de seguridad que enumera un conjunto de extremos que le gustaría que usara el servicio de enrutamiento en caso de que no se pueda alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="418d8-102">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="418d8-103">Si el primer extremo en la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista.</span><span class="sxs-lookup"><span data-stu-id="418d8-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="418d8-104">De este modo, dispone de una forma rápida de agregar confiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar modelos complejos o dónde implementar todos sus servicios.</span><span class="sxs-lookup"><span data-stu-id="418d8-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="418d8-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="418d8-105">\<system.serviceModel></span></span>  
<span data-ttu-id="418d8-106">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="418d8-106">\<routing></span></span>  
<span data-ttu-id="418d8-107">\<> backupLists</span><span class="sxs-lookup"><span data-stu-id="418d8-107">\<backupLists></span></span>  
<span data-ttu-id="418d8-108">\<> backupList</span><span class="sxs-lookup"><span data-stu-id="418d8-108">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="418d8-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="418d8-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="418d8-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="418d8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="418d8-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="418d8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="418d8-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="418d8-112">Attributes</span></span>  
  
|<span data-ttu-id="418d8-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="418d8-113">Attribute</span></span>|<span data-ttu-id="418d8-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="418d8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="418d8-115">name</span><span class="sxs-lookup"><span data-stu-id="418d8-115">name</span></span>|<span data-ttu-id="418d8-116">Cadena que especifica el nombre usado para identificar esta lista de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="418d8-116">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="418d8-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="418d8-117">Child Elements</span></span>  
  
|<span data-ttu-id="418d8-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="418d8-118">Element</span></span>|<span data-ttu-id="418d8-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="418d8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="418d8-120">\<filter></span><span class="sxs-lookup"><span data-stu-id="418d8-120">\<filter></span></span>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="418d8-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="418d8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="418d8-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="418d8-122">Element</span></span>|<span data-ttu-id="418d8-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="418d8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="418d8-124">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="418d8-124">\<routing></span></span>](routing.md)|<span data-ttu-id="418d8-125">Lista de extremos auxiliares.</span><span class="sxs-lookup"><span data-stu-id="418d8-125">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="418d8-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="418d8-126">Remarks</span></span>  
 <span data-ttu-id="418d8-127">Esta sección contiene una colección ordenada de extremos a los que se transmitirá un mensaje en caso de que se produzca una excepción de comunicaciones cuando se envíe al extremo primario.</span><span class="sxs-lookup"><span data-stu-id="418d8-127">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="418d8-128">Si un envío al punto de conexión principal que aparece `endpointName` en el atributo de [ \<agregar >](add-of-entries.md) produce un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al primer punto de conexión en esta sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="418d8-128">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="418d8-129">Si esto también genera un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al siguiente mensaje que contiene esta sección hasta que el intento de envío se realice correctamente, que devuelva un error distinto de una excepción de comunicaciones o que todos los puntos de conexión de la colección hayan devuelto un error.</span><span class="sxs-lookup"><span data-stu-id="418d8-129">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="418d8-130">En el ejemplo siguiente, si un envío al punto de conexión principal denominado "Destination" devuelve una excepción de comunicación, el servicio intentará enviar el mensaje a "alternateServiceQueue".</span><span class="sxs-lookup"><span data-stu-id="418d8-130">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="418d8-131">Si este intento también devuelve una excepción de comunicación, el servicio de enrutamiento intentará enviar el mensaje al punto de conexión siguiente de la colección.</span><span class="sxs-lookup"><span data-stu-id="418d8-131">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="418d8-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="418d8-132">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
