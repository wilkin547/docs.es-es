---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 478211755b9131c03b72777ee95ff7223b9092c9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850274"
---
# <a name="backuplist"></a><span data-ttu-id="42039-101">\<> backupList</span><span class="sxs-lookup"><span data-stu-id="42039-101">\<backupList></span></span>
<span data-ttu-id="42039-102">Representa una sección de configuración para definir una lista de copia de seguridad que enumera un conjunto de extremos que le gustaría que usara el servicio de enrutamiento en caso de que no se pueda alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="42039-102">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="42039-103">Si el primer extremo en la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista.</span><span class="sxs-lookup"><span data-stu-id="42039-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="42039-104">De este modo, dispone de una forma rápida de agregar confiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar modelos complejos o dónde implementar todos sus servicios.</span><span class="sxs-lookup"><span data-stu-id="42039-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
<span data-ttu-id="42039-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="42039-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="42039-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="42039-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="42039-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enrutamiento**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="42039-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="42039-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> backupLists**](backuplists.md)</span><span class="sxs-lookup"><span data-stu-id="42039-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)</span></span>\
<span data-ttu-id="42039-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> backupList**</span><span class="sxs-lookup"><span data-stu-id="42039-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupList>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42039-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42039-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42039-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="42039-111">Attributes and Elements</span></span>  
 <span data-ttu-id="42039-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="42039-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42039-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="42039-113">Attributes</span></span>  
  
|<span data-ttu-id="42039-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="42039-114">Attribute</span></span>|<span data-ttu-id="42039-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="42039-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42039-116">Nombre</span><span class="sxs-lookup"><span data-stu-id="42039-116">name</span></span>|<span data-ttu-id="42039-117">Cadena que especifica el nombre usado para identificar esta lista de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="42039-117">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42039-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="42039-118">Child Elements</span></span>  
  
|<span data-ttu-id="42039-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="42039-119">Element</span></span>|<span data-ttu-id="42039-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="42039-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42039-121">\<filter></span><span class="sxs-lookup"><span data-stu-id="42039-121">\<filter></span></span>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="42039-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="42039-122">Parent Elements</span></span>  
  
|<span data-ttu-id="42039-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="42039-123">Element</span></span>|<span data-ttu-id="42039-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="42039-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42039-125">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="42039-125">\<routing></span></span>](routing.md)|<span data-ttu-id="42039-126">Lista de extremos auxiliares.</span><span class="sxs-lookup"><span data-stu-id="42039-126">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42039-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42039-127">Remarks</span></span>  
 <span data-ttu-id="42039-128">Esta sección contiene una colección ordenada de extremos a los que se transmitirá un mensaje en caso de que se produzca una excepción de comunicaciones cuando se envíe al extremo primario.</span><span class="sxs-lookup"><span data-stu-id="42039-128">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="42039-129">Si un envío al punto de conexión principal que aparece `endpointName` en el atributo de [ \<agregar >](add-of-entries.md) produce un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al primer punto de conexión en esta sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="42039-129">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="42039-130">Si esto también genera un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al siguiente mensaje que contiene esta sección hasta que el intento de envío se realice correctamente, que devuelva un error distinto de una excepción de comunicaciones o que todos los puntos de conexión de la colección hayan devuelto un error.</span><span class="sxs-lookup"><span data-stu-id="42039-130">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="42039-131">En el ejemplo siguiente, si un envío al punto de conexión principal denominado "Destination" devuelve una excepción de comunicación, el servicio intentará enviar el mensaje a "alternateServiceQueue".</span><span class="sxs-lookup"><span data-stu-id="42039-131">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="42039-132">Si este intento también devuelve una excepción de comunicación, el servicio de enrutamiento intentará enviar el mensaje al punto de conexión siguiente de la colección.</span><span class="sxs-lookup"><span data-stu-id="42039-132">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="42039-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="42039-133">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
