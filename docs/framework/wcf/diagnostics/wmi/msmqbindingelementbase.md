---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: e7f4cf41168bd1e5483524195e20541d896a6569
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183196"
---
# <a name="msmqbindingelementbase"></a><span data-ttu-id="a38cb-102">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="a38cb-102">MsmqBindingElementBase</span></span>
<span data-ttu-id="a38cb-103">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="a38cb-103">MsmqBindingElementBase</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a38cb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a38cb-104">Syntax</span></span>  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a38cb-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a38cb-105">Methods</span></span>  
 <span data-ttu-id="a38cb-106">La clase TraceListenerArgument no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="a38cb-106">The MsmqBindingElementBase class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a38cb-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a38cb-107">Properties</span></span>  
 <span data-ttu-id="a38cb-108">La clase MsmqBindingElementBase tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="a38cb-108">The MsmqBindingElementBase class has the following properties:</span></span>  
  
### <a name="customdeadletterqueue"></a><span data-ttu-id="a38cb-109">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="a38cb-109">CustomDeadLetterQueue</span></span>  
 <span data-ttu-id="a38cb-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="a38cb-110">Data type: string</span></span>  
  
 <span data-ttu-id="a38cb-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a38cb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a38cb-112">Un URI que contiene la ubicación de la cola de mensajes no enviados de cada aplicación, donde se colocan los mensajes que han expirado o cuya transferencia o envío han fallado.</span><span class="sxs-lookup"><span data-stu-id="a38cb-112">A URI that contains the location of the dead letter queue for each application, where messages that have expired or that have failed transfer or delivery are placed.</span></span>  
  
### <a name="deadletterqueue"></a><span data-ttu-id="a38cb-113">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="a38cb-113">DeadLetterQueue</span></span>  
 <span data-ttu-id="a38cb-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="a38cb-114">Data type: string</span></span>  
  
 <span data-ttu-id="a38cb-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a38cb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a38cb-116">Un valor de enumeración que indica el tipo de cola de mensajes no enviados que se ha de usar.</span><span class="sxs-lookup"><span data-stu-id="a38cb-116">An enumeration value that indicates the type of dead letter queue to use.</span></span>  
  
### <a name="durable"></a><span data-ttu-id="a38cb-117">Durable</span><span class="sxs-lookup"><span data-stu-id="a38cb-117">Durable</span></span>  
 <span data-ttu-id="a38cb-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="a38cb-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="a38cb-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a38cb-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a38cb-120">Un valor que indica si los mensajes procesados por este enlace son duraderos o volátiles.</span><span class="sxs-lookup"><span data-stu-id="a38cb-120">A value that indicates whether the messages processed by this binding are durable or volatile.</span></span>  
  
### <a name="exactlyonce"></a><span data-ttu-id="a38cb-121">ExactlyOnce</span><span class="sxs-lookup"><span data-stu-id="a38cb-121">ExactlyOnce</span></span>  
 <span data-ttu-id="a38cb-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="a38cb-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="a38cb-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a38cb-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a38cb-124">Un valor booleano que indica si los mensajes procesados por este enlace se reciben solo una vez.</span><span class="sxs-lookup"><span data-stu-id="a38cb-124">A Boolean value that indicates whether messages processed by this binding are received exactly once.</span></span>  
  
### <a name="maxretrycycles"></a><span data-ttu-id="a38cb-125">MaxRetryCycles</span><span class="sxs-lookup"><span data-stu-id="a38cb-125">MaxRetryCycles</span></span>  
 <span data-ttu-id="a38cb-126">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="a38cb-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="a38cb-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a38cb-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a38cb-128">El número máximo de ciclos de reintento de entrega de mensajes a la aplicación receptora.</span><span class="sxs-lookup"><span data-stu-id="a38cb-128">The maximum number of retry cycles to attempt delivery of messages to the receiving application.</span></span>  
  
### <a name="receiveerrorhandling"></a><span data-ttu-id="a38cb-129">ReceiveErrorHandling</span><span class="sxs-lookup"><span data-stu-id="a38cb-129">ReceiveErrorHandling</span></span>  
 <span data-ttu-id="a38cb-130">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="a38cb-130">Data type: string</span></span>  
  
 <span data-ttu-id="a38cb-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a38cb-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a38cb-132">Los valores para el control de mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="a38cb-132">The settings for poison message handling.</span></span>  
  
### <a name="receiveretrycount"></a><span data-ttu-id="a38cb-133">ReceiveRetryCount</span><span class="sxs-lookup"><span data-stu-id="a38cb-133">ReceiveRetryCount</span></span>  
 <span data-ttu-id="a38cb-134">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="a38cb-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="a38cb-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a38cb-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a38cb-136">El número máximo de intentos de reintento inmediato en un mensaje que se lee desde la cola de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a38cb-136">The maximum number of immediate retry attempts on a message that is read from the application queue.</span></span>  
  
### <a name="retrycycledelay"></a><span data-ttu-id="a38cb-137">RetryCycleDelay</span><span class="sxs-lookup"><span data-stu-id="a38cb-137">RetryCycleDelay</span></span>  
 <span data-ttu-id="a38cb-138">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="a38cb-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="a38cb-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a38cb-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a38cb-140">Un valor que indica el tiempo de retardo entre los ciclos de reintento al intentar entregar un mensaje que no se pudo entregar inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a38cb-140">A value that indicates the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span>  
  
### <a name="timetolive"></a><span data-ttu-id="a38cb-141">TimeToLive</span><span class="sxs-lookup"><span data-stu-id="a38cb-141">TimeToLive</span></span>  
 <span data-ttu-id="a38cb-142">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="a38cb-142">Data type: datetime</span></span>  
  
 <span data-ttu-id="a38cb-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a38cb-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a38cb-144">El intervalo de tiempo que indica cuánto tiempo pueden estar en la cola los mensajes procesados por este enlace antes de expirar.</span><span class="sxs-lookup"><span data-stu-id="a38cb-144">The interval of time that indicates how long the messages processed by this binding can be in the queue before they expire.</span></span>  
  
### <a name="usemsmqtracing"></a><span data-ttu-id="a38cb-145">UseMsmqTracing</span><span class="sxs-lookup"><span data-stu-id="a38cb-145">UseMsmqTracing</span></span>  
 <span data-ttu-id="a38cb-146">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="a38cb-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="a38cb-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a38cb-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a38cb-148">Un valor booleano que indica si los mensajes procesados por este enlace se deberían seguir paso a paso.</span><span class="sxs-lookup"><span data-stu-id="a38cb-148">A Boolean value that indicates whether messages processed by this binding should be traced.</span></span>  
  
### <a name="usesourcejournal"></a><span data-ttu-id="a38cb-149">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="a38cb-149">UseSourceJournal</span></span>  
 <span data-ttu-id="a38cb-150">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="a38cb-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="a38cb-151">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a38cb-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a38cb-152">Un valor booleano que indica si las copias de mensajes procesados por este enlace deberían almacenarse en la cola de diario de origen.</span><span class="sxs-lookup"><span data-stu-id="a38cb-152">A Boolean value that indicates whether copies of messages processed by this binding should be stored in the source journal queue.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a38cb-153">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a38cb-153">Requirements</span></span>  
  
|<span data-ttu-id="a38cb-154">MOF</span><span class="sxs-lookup"><span data-stu-id="a38cb-154">MOF</span></span>|<span data-ttu-id="a38cb-155">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a38cb-155">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a38cb-156">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a38cb-156">Namespace</span></span>|<span data-ttu-id="a38cb-157">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a38cb-157">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a38cb-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="a38cb-158">See Also</span></span>  
 <xref:System.ServiceModel.NetMsmqBinding>  
 <xref:System.ServiceModel.MsmqBindingBase>
