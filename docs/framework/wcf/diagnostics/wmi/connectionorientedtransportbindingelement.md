---
description: 'Más información acerca de: ConnectionOrientedTransportBindingElement'
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: bd0c05fc86ad7bc95837cee7e22ea83975369b62
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757584"
---
# <a name="connectionorientedtransportbindingelement"></a><span data-ttu-id="fa2ac-103">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="fa2ac-103">ConnectionOrientedTransportBindingElement</span></span>

<span data-ttu-id="fa2ac-104">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="fa2ac-104">ConnectionOrientedTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa2ac-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa2ac-105">Syntax</span></span>  
  
```csharp
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fa2ac-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="fa2ac-106">Methods</span></span>  

 <span data-ttu-id="fa2ac-107">La clase ConnectionOrientedTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="fa2ac-107">The ConnectionOrientedTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fa2ac-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fa2ac-108">Properties</span></span>  

 <span data-ttu-id="fa2ac-109">La clase ConnectionOrientedTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="fa2ac-109">The ConnectionOrientedTransportBindingElement class has the following properties:</span></span>  
  
### <a name="channelinitializationtimeout"></a><span data-ttu-id="fa2ac-110">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="fa2ac-110">ChannelInitializationTimeout</span></span>  

 <span data-ttu-id="fa2ac-111">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="fa2ac-111">Data type: datetime</span></span>  
  
 <span data-ttu-id="fa2ac-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fa2ac-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fa2ac-113">El timespan que especifica cuánto tiempo tiene la inicialización del canal para completarse antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="fa2ac-113">The timespan that specifies how long the channel initialization has to complete before timing out.</span></span>  
  
### <a name="connectionbuffersize"></a><span data-ttu-id="fa2ac-114">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="fa2ac-114">ConnectionBufferSize</span></span>  

 <span data-ttu-id="fa2ac-115">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="fa2ac-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="fa2ac-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fa2ac-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fa2ac-117">El tamaño del búfer usado para transmitir un fragmento del mensaje serializado en la conexión del cliente o servicio.</span><span class="sxs-lookup"><span data-stu-id="fa2ac-117">The size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="fa2ac-118">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="fa2ac-118">HostNameComparisonMode</span></span>  

 <span data-ttu-id="fa2ac-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="fa2ac-119">Data type: string</span></span>  
  
 <span data-ttu-id="fa2ac-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fa2ac-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fa2ac-121">Un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.</span><span class="sxs-lookup"><span data-stu-id="fa2ac-121">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="fa2ac-122">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="fa2ac-122">MaxBufferSize</span></span>  

 <span data-ttu-id="fa2ac-123">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="fa2ac-123">Data type: sint32</span></span>  
  
 <span data-ttu-id="fa2ac-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fa2ac-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fa2ac-125">El tamaño máximo del búfer que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="fa2ac-125">The maximum size of the buffer to use.</span></span>  
  
### <a name="maxoutputdelay"></a><span data-ttu-id="fa2ac-126">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="fa2ac-126">MaxOutputDelay</span></span>  

 <span data-ttu-id="fa2ac-127">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="fa2ac-127">Data type: datetime</span></span>  
  
 <span data-ttu-id="fa2ac-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fa2ac-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fa2ac-129">El intervalo máximo de tiempo que un fragmento de un mensaje o un mensaje completo pueden estar almacenados en búfer en memoria antes de que se envíen.</span><span class="sxs-lookup"><span data-stu-id="fa2ac-129">The maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>  
  
### <a name="maxpendingaccepts"></a><span data-ttu-id="fa2ac-130">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="fa2ac-130">MaxPendingAccepts</span></span>  

 <span data-ttu-id="fa2ac-131">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="fa2ac-131">Data type: sint32</span></span>  
  
 <span data-ttu-id="fa2ac-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fa2ac-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fa2ac-133">El número máximo de subprocesos de aceptación asincrónica pendientes disponibles para procesar conexiones entrantes en el servicio.</span><span class="sxs-lookup"><span data-stu-id="fa2ac-133">The maximum number of pending asynchronous accept threads that are available for processing incoming connections on the service.</span></span>  
  
### <a name="maxpendingconnections"></a><span data-ttu-id="fa2ac-134">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="fa2ac-134">MaxPendingConnections</span></span>  

 <span data-ttu-id="fa2ac-135">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="fa2ac-135">Data type: sint32</span></span>  
  
 <span data-ttu-id="fa2ac-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fa2ac-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fa2ac-137">El número máximo de conexiones pendientes.</span><span class="sxs-lookup"><span data-stu-id="fa2ac-137">The maximum number of pending connections.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="fa2ac-138">TransferMode</span><span class="sxs-lookup"><span data-stu-id="fa2ac-138">TransferMode</span></span>  

 <span data-ttu-id="fa2ac-139">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="fa2ac-139">Data type: string</span></span>  
  
 <span data-ttu-id="fa2ac-140">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fa2ac-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fa2ac-141">Un valor que especifica si los mensajes están almacenados en búfer o se transmiten mediante el transporte orientado a la conexión.</span><span class="sxs-lookup"><span data-stu-id="fa2ac-141">A value that specifies whether the messages are buffered or streamed with the connection-oriented transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa2ac-142">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa2ac-142">Requirements</span></span>  
  
|<span data-ttu-id="fa2ac-143">MOF</span><span class="sxs-lookup"><span data-stu-id="fa2ac-143">MOF</span></span>|<span data-ttu-id="fa2ac-144">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fa2ac-144">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fa2ac-145">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="fa2ac-145">Namespace</span></span>|<span data-ttu-id="fa2ac-146">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fa2ac-146">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa2ac-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa2ac-147">See also</span></span>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
