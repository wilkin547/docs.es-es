---
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: 2e2e36486c3788cd714ffd0ed545fbb14f831476
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50038898"
---
# <a name="reliablesessionbindingelement"></a><span data-ttu-id="31be8-102">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="31be8-102">ReliableSessionBindingElement</span></span>
<span data-ttu-id="31be8-103">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="31be8-103">ReliableSessionBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31be8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31be8-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="31be8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="31be8-105">Methods</span></span>  
 <span data-ttu-id="31be8-106">La clase ReliableSessionBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="31be8-106">The ReliableSessionBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="31be8-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="31be8-107">Properties</span></span>  
 <span data-ttu-id="31be8-108">La clase ReliableSessionBindingElement posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="31be8-108">The ReliableSessionBindingElement class has the following properties:</span></span>  
  
### <a name="acknowledgementinterval"></a><span data-ttu-id="31be8-109">AcknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="31be8-109">AcknowledgementInterval</span></span>  
 <span data-ttu-id="31be8-110">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="31be8-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="31be8-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="31be8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="31be8-112">Intervalo de tiempo que un destino espera antes de enviar una confirmación al origen del mensaje en canales de confianza creados por el que generador.</span><span class="sxs-lookup"><span data-stu-id="31be8-112">The interval of time that a destination waits before sending an acknowledgement to the message source on reliable channels that are created by the factory.</span></span>  
  
### <a name="flowcontrolenabled"></a><span data-ttu-id="31be8-113">FlowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="31be8-113">FlowControlEnabled</span></span>  
 <span data-ttu-id="31be8-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="31be8-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="31be8-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="31be8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="31be8-116">Valor booleano que especifica si el control de flujo está habilitado.</span><span class="sxs-lookup"><span data-stu-id="31be8-116">A Boolean value that specifies whether flow control is enabled.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="31be8-117">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="31be8-117">InactivityTimeout</span></span>  
 <span data-ttu-id="31be8-118">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="31be8-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="31be8-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="31be8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="31be8-120">Especifica la duración máxima durante la cual el canal permite a la otra parte de la comunicación no enviar ningún mensaje antes de que se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="31be8-120">Specifies the maximum duration the channel is going to allow the other communicating party not to send any messages before faulting the channel.</span></span>  
  
### <a name="maxpendingchannels"></a><span data-ttu-id="31be8-121">MaxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="31be8-121">MaxPendingChannels</span></span>  
 <span data-ttu-id="31be8-122">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="31be8-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="31be8-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="31be8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="31be8-124">Número máximo de canales que pueden esperar a ser aceptados en el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="31be8-124">The maximum number of channels that can wait to be accepted on the listener.</span></span>  
  
### <a name="maxretrycount"></a><span data-ttu-id="31be8-125">MaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="31be8-125">MaxRetryCount</span></span>  
 <span data-ttu-id="31be8-126">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="31be8-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="31be8-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="31be8-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="31be8-128">Número máximo de veces que un canal de confianza intenta retransmitir un mensaje, para él que no ha recibido una confirmación, llamando a `Send` en su canal subyacente.</span><span class="sxs-lookup"><span data-stu-id="31be8-128">The maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgement for, by calling `Send` on its underlying channel.</span></span>  
  
### <a name="maxtransferwindowsize"></a><span data-ttu-id="31be8-129">MaxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="31be8-129">MaxTransferWindowSize</span></span>  
 <span data-ttu-id="31be8-130">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="31be8-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="31be8-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="31be8-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="31be8-132">El tamaño máximo de la ventana de transferencia para la sesión de confianza.</span><span class="sxs-lookup"><span data-stu-id="31be8-132">The maximum transfer window size for the reliable session.</span></span>  
  
### <a name="ordered"></a><span data-ttu-id="31be8-133">Por orden </span><span class="sxs-lookup"><span data-stu-id="31be8-133">Ordered</span></span>  
 <span data-ttu-id="31be8-134">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="31be8-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="31be8-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="31be8-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="31be8-136">Un valor booleano que especifica si se garantiza que los mensajes lleguen en el orden en el que fueron enviados.</span><span class="sxs-lookup"><span data-stu-id="31be8-136">A Boolean value that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span>  
  
### <a name="reliablemessagingversion"></a><span data-ttu-id="31be8-137">ReliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="31be8-137">ReliableMessagingVersion</span></span>  
 <span data-ttu-id="31be8-138">Tipo de datos: enteros</span><span class="sxs-lookup"><span data-stu-id="31be8-138">Data type: integer</span></span>  
  
 <span data-ttu-id="31be8-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="31be8-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="31be8-140">Entero que especifica la versión de protocolo de WS-ReliableMessaging utilizado en la sesión de confianza.</span><span class="sxs-lookup"><span data-stu-id="31be8-140">An integer that specifies the WS-ReliableMessaging protocol version used in the reliable session.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31be8-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31be8-141">Requirements</span></span>  
  
|<span data-ttu-id="31be8-142">MOF</span><span class="sxs-lookup"><span data-stu-id="31be8-142">MOF</span></span>|<span data-ttu-id="31be8-143">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="31be8-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="31be8-144">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="31be8-144">Namespace</span></span>|<span data-ttu-id="31be8-145">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="31be8-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31be8-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="31be8-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
