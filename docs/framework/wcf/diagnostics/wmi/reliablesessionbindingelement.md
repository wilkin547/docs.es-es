---
description: 'Más información acerca de: ReliableSessionBindingElement'
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: 582fd62a8751a31c2834b7d81219a237c9887236
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743868"
---
# <a name="reliablesessionbindingelement"></a><span data-ttu-id="f26d1-103">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="f26d1-103">ReliableSessionBindingElement</span></span>

<span data-ttu-id="f26d1-104">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="f26d1-104">ReliableSessionBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f26d1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f26d1-105">Syntax</span></span>  
  
```csharp
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f26d1-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="f26d1-106">Methods</span></span>  

 <span data-ttu-id="f26d1-107">La clase ReliableSessionBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="f26d1-107">The ReliableSessionBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f26d1-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f26d1-108">Properties</span></span>  

 <span data-ttu-id="f26d1-109">La clase ReliableSessionBindingElement posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f26d1-109">The ReliableSessionBindingElement class has the following properties:</span></span>  
  
### <a name="acknowledgementinterval"></a><span data-ttu-id="f26d1-110">AcknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="f26d1-110">AcknowledgementInterval</span></span>  

 <span data-ttu-id="f26d1-111">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="f26d1-111">Data type: datetime</span></span>  
  
 <span data-ttu-id="f26d1-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f26d1-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f26d1-113">Intervalo de tiempo que un destino espera antes de enviar una confirmación al origen del mensaje en canales de confianza creados por el que generador.</span><span class="sxs-lookup"><span data-stu-id="f26d1-113">The interval of time that a destination waits before sending an acknowledgement to the message source on reliable channels that are created by the factory.</span></span>  
  
### <a name="flowcontrolenabled"></a><span data-ttu-id="f26d1-114">FlowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="f26d1-114">FlowControlEnabled</span></span>  

 <span data-ttu-id="f26d1-115">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="f26d1-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="f26d1-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f26d1-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f26d1-117">Valor booleano que especifica si el control de flujo está habilitado.</span><span class="sxs-lookup"><span data-stu-id="f26d1-117">A Boolean value that specifies whether flow control is enabled.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="f26d1-118">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="f26d1-118">InactivityTimeout</span></span>  

 <span data-ttu-id="f26d1-119">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="f26d1-119">Data type: datetime</span></span>  
  
 <span data-ttu-id="f26d1-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f26d1-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f26d1-121">Especifica la duración máxima durante la cual el canal permite a la otra parte de la comunicación no enviar ningún mensaje antes de que se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="f26d1-121">Specifies the maximum duration the channel is going to allow the other communicating party not to send any messages before faulting the channel.</span></span>  
  
### <a name="maxpendingchannels"></a><span data-ttu-id="f26d1-122">MaxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="f26d1-122">MaxPendingChannels</span></span>  

 <span data-ttu-id="f26d1-123">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="f26d1-123">Data type: sint32</span></span>  
  
 <span data-ttu-id="f26d1-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f26d1-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f26d1-125">Número máximo de canales que pueden esperar a ser aceptados en el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="f26d1-125">The maximum number of channels that can wait to be accepted on the listener.</span></span>  
  
### <a name="maxretrycount"></a><span data-ttu-id="f26d1-126">MaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="f26d1-126">MaxRetryCount</span></span>  

 <span data-ttu-id="f26d1-127">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="f26d1-127">Data type: sint32</span></span>  
  
 <span data-ttu-id="f26d1-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f26d1-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f26d1-129">Número máximo de veces que un canal de confianza intenta retransmitir un mensaje, para él que no ha recibido una confirmación, llamando a `Send` en su canal subyacente.</span><span class="sxs-lookup"><span data-stu-id="f26d1-129">The maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgement for, by calling `Send` on its underlying channel.</span></span>  
  
### <a name="maxtransferwindowsize"></a><span data-ttu-id="f26d1-130">MaxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="f26d1-130">MaxTransferWindowSize</span></span>  

 <span data-ttu-id="f26d1-131">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="f26d1-131">Data type: sint32</span></span>  
  
 <span data-ttu-id="f26d1-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f26d1-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f26d1-133">El tamaño máximo de la ventana de transferencia para la sesión de confianza.</span><span class="sxs-lookup"><span data-stu-id="f26d1-133">The maximum transfer window size for the reliable session.</span></span>  
  
### <a name="ordered"></a><span data-ttu-id="f26d1-134">Ordered (Realizado)</span><span class="sxs-lookup"><span data-stu-id="f26d1-134">Ordered</span></span>  

 <span data-ttu-id="f26d1-135">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="f26d1-135">Data type: boolean</span></span>  
  
 <span data-ttu-id="f26d1-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f26d1-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f26d1-137">Un valor booleano que especifica si se garantiza que los mensajes lleguen en el orden en el que fueron enviados.</span><span class="sxs-lookup"><span data-stu-id="f26d1-137">A Boolean value that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span>  
  
### <a name="reliablemessagingversion"></a><span data-ttu-id="f26d1-138">ReliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="f26d1-138">ReliableMessagingVersion</span></span>  

 <span data-ttu-id="f26d1-139">Tipo de datos: enteros</span><span class="sxs-lookup"><span data-stu-id="f26d1-139">Data type: integer</span></span>  
  
 <span data-ttu-id="f26d1-140">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f26d1-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f26d1-141">Entero que especifica la versión de protocolo de WS-ReliableMessaging utilizado en la sesión de confianza.</span><span class="sxs-lookup"><span data-stu-id="f26d1-141">An integer that specifies the WS-ReliableMessaging protocol version used in the reliable session.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f26d1-142">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f26d1-142">Requirements</span></span>  
  
|<span data-ttu-id="f26d1-143">MOF</span><span class="sxs-lookup"><span data-stu-id="f26d1-143">MOF</span></span>|<span data-ttu-id="f26d1-144">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f26d1-144">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f26d1-145">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f26d1-145">Namespace</span></span>|<span data-ttu-id="f26d1-146">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f26d1-146">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f26d1-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="f26d1-147">See also</span></span>

- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
