---
title: '&lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 6684dcc485ef1ee2c3e5501f2fbc43898e172958
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltbackuplistgt"></a><span data-ttu-id="bbb65-102">&lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="bbb65-102">&lt;backupList&gt;</span></span>
<span data-ttu-id="bbb65-103">Representa una sección de configuración para definir una lista auxiliar que enumera un conjunto de extremos que desea que el servicio de enrutamiento para usar en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="bbb65-103">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="bbb65-104">Si el primer punto de conexión en la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista.</span><span class="sxs-lookup"><span data-stu-id="bbb65-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="bbb65-105">De este modo, dispone de una forma rápida de agregar confiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar modelos complejos o dónde implementar todos sus servicios.</span><span class="sxs-lookup"><span data-stu-id="bbb65-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="bbb65-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bbb65-106">\<system.serviceModel></span></span>  
<span data-ttu-id="bbb65-107">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="bbb65-107">\<routing></span></span>  
<span data-ttu-id="bbb65-108">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="bbb65-108">\<backupLists></span></span>  
<span data-ttu-id="bbb65-109">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="bbb65-109">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbb65-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bbb65-110">Syntax</span></span>  
  
```xml 
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bbb65-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bbb65-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bbb65-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bbb65-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bbb65-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="bbb65-113">Attributes</span></span>  
  
|<span data-ttu-id="bbb65-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="bbb65-114">Attribute</span></span>|<span data-ttu-id="bbb65-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="bbb65-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bbb65-116">name</span><span class="sxs-lookup"><span data-stu-id="bbb65-116">name</span></span>|<span data-ttu-id="bbb65-117">Cadena que especifica el nombre usado para identificar esta lista de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="bbb65-117">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bbb65-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bbb65-118">Child Elements</span></span>  
  
|<span data-ttu-id="bbb65-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="bbb65-119">Element</span></span>|<span data-ttu-id="bbb65-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="bbb65-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bbb65-121">\<filter></span><span class="sxs-lookup"><span data-stu-id="bbb65-121">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="bbb65-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bbb65-122">Parent Elements</span></span>  
  
|<span data-ttu-id="bbb65-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="bbb65-123">Element</span></span>|<span data-ttu-id="bbb65-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="bbb65-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bbb65-125">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="bbb65-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="bbb65-126">Lista de puntos de conexión auxiliares.</span><span class="sxs-lookup"><span data-stu-id="bbb65-126">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbb65-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bbb65-127">Remarks</span></span>  
 <span data-ttu-id="bbb65-128">Esta sección contiene una colección ordenada de puntos de conexión a los que se transmitirá un mensaje en caso de que se produzca una excepción de comunicaciones cuando se envíe al punto de conexión primario.</span><span class="sxs-lookup"><span data-stu-id="bbb65-128">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="bbb65-129">Si un envío al punto de conexión principal aparece en la `endpointName` atributo de [ \<Agregar >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) se produce una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al primer extremo en este sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="bbb65-129">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="bbb65-130">Si esto también genera un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al siguiente mensaje que contiene esta sección hasta que el intento de envío se realice correctamente, que devuelva un error distinto de una excepción de comunicaciones o que todos los puntos de conexión de la colección hayan devuelto un error.</span><span class="sxs-lookup"><span data-stu-id="bbb65-130">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="bbb65-131">En el siguiente ejemplo, si un envío al extremo primario denominado "Destino" devuelve una excepción de comunicación, el servicio intentará enviar el mensaje a "alternateServiceQueue".</span><span class="sxs-lookup"><span data-stu-id="bbb65-131">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="bbb65-132">Si este intento también devuelve una excepción de comunicación, el servicio de enrutamiento intentará enviar el mensaje al punto de conexión siguiente de la colección.</span><span class="sxs-lookup"><span data-stu-id="bbb65-132">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bbb65-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbb65-133">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
