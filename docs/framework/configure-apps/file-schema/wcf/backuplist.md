---
description: 'Más información acerca de: <backupList>'
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 5323c8dad827ebb95e3cad65b3ad527d04517e3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749719"
---
# \<backupList>

<span data-ttu-id="73a3c-102">Representa una sección de configuración para definir una lista auxiliar que enumera un conjunto de puntos de conexión que le gustaría que usara el servicio de enrutamiento en caso de que no se pueda alcanzar el punto de conexión primario.</span><span class="sxs-lookup"><span data-stu-id="73a3c-102">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="73a3c-103">Si el primer extremo en la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista.</span><span class="sxs-lookup"><span data-stu-id="73a3c-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="73a3c-104">De este modo, dispone de una forma rápida de agregar confiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar modelos complejos o dónde implementar todos sus servicios.</span><span class="sxs-lookup"><span data-stu-id="73a3c-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupList>**  
  
## <a name="syntax"></a><span data-ttu-id="73a3c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73a3c-105">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73a3c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="73a3c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="73a3c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="73a3c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73a3c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="73a3c-108">Attributes</span></span>  
  
|<span data-ttu-id="73a3c-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="73a3c-109">Attribute</span></span>|<span data-ttu-id="73a3c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="73a3c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73a3c-111">name</span><span class="sxs-lookup"><span data-stu-id="73a3c-111">name</span></span>|<span data-ttu-id="73a3c-112">Cadena que especifica el nombre usado para identificar esta lista de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="73a3c-112">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73a3c-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="73a3c-113">Child Elements</span></span>  
  
|<span data-ttu-id="73a3c-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="73a3c-114">Element</span></span>|<span data-ttu-id="73a3c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="73a3c-115">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="73a3c-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="73a3c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="73a3c-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="73a3c-117">Element</span></span>|<span data-ttu-id="73a3c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="73a3c-118">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="73a3c-119">Lista de extremos auxiliares.</span><span class="sxs-lookup"><span data-stu-id="73a3c-119">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73a3c-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="73a3c-120">Remarks</span></span>  

 <span data-ttu-id="73a3c-121">Esta sección contiene una colección ordenada de extremos a los que se transmitirá un mensaje en caso de que se produzca una excepción de comunicaciones cuando se envíe al extremo primario.</span><span class="sxs-lookup"><span data-stu-id="73a3c-121">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="73a3c-122">Si un envío al punto de conexión principal que aparece en el `endpointName` atributo de [\<add>](add-of-entries.md) produce un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al primer punto de conexión en esta sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="73a3c-122">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="73a3c-123">Si esto también genera un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al siguiente mensaje que contiene esta sección hasta que el intento de envío se realice correctamente, que devuelva un error distinto de una excepción de comunicaciones o que todos los puntos de conexión de la colección hayan devuelto un error.</span><span class="sxs-lookup"><span data-stu-id="73a3c-123">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="73a3c-124">En el ejemplo siguiente, si un envío al punto de conexión principal denominado "Destination" devuelve una excepción de comunicación, el servicio intentará enviar el mensaje a "alternateServiceQueue".</span><span class="sxs-lookup"><span data-stu-id="73a3c-124">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="73a3c-125">Si este intento también devuelve una excepción de comunicación, el servicio de enrutamiento intentará enviar el mensaje al punto de conexión siguiente de la colección.</span><span class="sxs-lookup"><span data-stu-id="73a3c-125">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73a3c-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="73a3c-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
