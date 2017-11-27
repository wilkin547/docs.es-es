---
title: ConnectionOrientedTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d28bedb67850b9bb77c25c8d29c6e39b056770a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="connectionorientedtransportbindingelement"></a><span data-ttu-id="e6610-102">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="e6610-102">ConnectionOrientedTransportBindingElement</span></span>
<span data-ttu-id="e6610-103">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="e6610-103">ConnectionOrientedTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6610-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6610-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="e6610-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e6610-105">Methods</span></span>  
 <span data-ttu-id="e6610-106">La clase ConnectionOrientedTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="e6610-106">The ConnectionOrientedTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e6610-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e6610-107">Properties</span></span>  
 <span data-ttu-id="e6610-108">La clase ConnectionOrientedTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6610-108">The ConnectionOrientedTransportBindingElement class has the following properties:</span></span>  
  
### <a name="channelinitializationtimeout"></a><span data-ttu-id="e6610-109">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="e6610-109">ChannelInitializationTimeout</span></span>  
 <span data-ttu-id="e6610-110">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="e6610-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="e6610-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e6610-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e6610-112">El timespan que especifica cuánto tiempo tiene la inicialización del canal para completarse antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="e6610-112">The timespan that specifies how long the channel initialization has to complete before timing out.</span></span>  
  
### <a name="connectionbuffersize"></a><span data-ttu-id="e6610-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="e6610-113">ConnectionBufferSize</span></span>  
 <span data-ttu-id="e6610-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="e6610-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="e6610-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e6610-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e6610-116">El tamaño del búfer usado para transmitir un fragmento del mensaje serializado en la conexión del cliente o servicio.</span><span class="sxs-lookup"><span data-stu-id="e6610-116">The size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="e6610-117">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="e6610-117">HostNameComparisonMode</span></span>  
 <span data-ttu-id="e6610-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e6610-118">Data type: string</span></span>  
  
 <span data-ttu-id="e6610-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e6610-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e6610-120">Un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.</span><span class="sxs-lookup"><span data-stu-id="e6610-120">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="e6610-121">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="e6610-121">MaxBufferSize</span></span>  
 <span data-ttu-id="e6610-122">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="e6610-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="e6610-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e6610-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e6610-124">El tamaño máximo del búfer que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e6610-124">The maximum size of the buffer to use.</span></span>  
  
### <a name="maxoutputdelay"></a><span data-ttu-id="e6610-125">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="e6610-125">MaxOutputDelay</span></span>  
 <span data-ttu-id="e6610-126">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="e6610-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="e6610-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e6610-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e6610-128">El intervalo máximo de tiempo que un fragmento de un mensaje o un mensaje completo pueden estar almacenados en búfer en memoria antes de que se envíen.</span><span class="sxs-lookup"><span data-stu-id="e6610-128">The maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>  
  
### <a name="maxpendingaccepts"></a><span data-ttu-id="e6610-129">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="e6610-129">MaxPendingAccepts</span></span>  
 <span data-ttu-id="e6610-130">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="e6610-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="e6610-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e6610-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e6610-132">El número máximo de subprocesos de aceptación asincrónica pendientes disponibles para procesar conexiones entrantes en el servicio.</span><span class="sxs-lookup"><span data-stu-id="e6610-132">The maximum number of pending asynchronous accept threads that are available for processing incoming connections on the service.</span></span>  
  
### <a name="maxpendingconnections"></a><span data-ttu-id="e6610-133">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="e6610-133">MaxPendingConnections</span></span>  
 <span data-ttu-id="e6610-134">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="e6610-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="e6610-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e6610-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e6610-136">El número máximo de conexiones pendientes.</span><span class="sxs-lookup"><span data-stu-id="e6610-136">The maximum number of pending connections.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="e6610-137">TransferMode</span><span class="sxs-lookup"><span data-stu-id="e6610-137">TransferMode</span></span>  
 <span data-ttu-id="e6610-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e6610-138">Data type: string</span></span>  
  
 <span data-ttu-id="e6610-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e6610-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e6610-140">Un valor que especifica si los mensajes están almacenados en búfer o se transmiten mediante el transporte orientado a la conexión.</span><span class="sxs-lookup"><span data-stu-id="e6610-140">A value that specifies whether the messages are buffered or streamed with the connection-oriented transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6610-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6610-141">Requirements</span></span>  
  
|<span data-ttu-id="e6610-142">MOF</span><span class="sxs-lookup"><span data-stu-id="e6610-142">MOF</span></span>|<span data-ttu-id="e6610-143">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e6610-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e6610-144">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e6610-144">Namespace</span></span>|<span data-ttu-id="e6610-145">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e6610-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6610-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6610-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
