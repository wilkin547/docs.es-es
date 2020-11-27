---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: 48d26bfa9074fd605e3545579f0bdc2744dfc7d8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267865"
---
# <a name="msmqbindingelementbase"></a><span data-ttu-id="366db-102">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="366db-102">MsmqBindingElementBase</span></span>

<span data-ttu-id="366db-103">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="366db-103">MsmqBindingElementBase</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="366db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="366db-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="366db-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="366db-105">Methods</span></span>  

 <span data-ttu-id="366db-106">La clase TraceListenerArgument no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="366db-106">The MsmqBindingElementBase class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="366db-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="366db-107">Properties</span></span>  

 <span data-ttu-id="366db-108">La clase MsmqBindingElementBase tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="366db-108">The MsmqBindingElementBase class has the following properties:</span></span>  
  
### <a name="customdeadletterqueue"></a><span data-ttu-id="366db-109">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="366db-109">CustomDeadLetterQueue</span></span>  

 <span data-ttu-id="366db-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="366db-110">Data type: string</span></span>  
  
 <span data-ttu-id="366db-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="366db-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="366db-112">Un URI que contiene la ubicación de la cola de mensajes no enviados de cada aplicación, donde se colocan los mensajes que han expirado o cuya transferencia o envío han fallado.</span><span class="sxs-lookup"><span data-stu-id="366db-112">A URI that contains the location of the dead letter queue for each application, where messages that have expired or that have failed transfer or delivery are placed.</span></span>  
  
### <a name="deadletterqueue"></a><span data-ttu-id="366db-113">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="366db-113">DeadLetterQueue</span></span>  

 <span data-ttu-id="366db-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="366db-114">Data type: string</span></span>  
  
 <span data-ttu-id="366db-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="366db-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="366db-116">Un valor de enumeración que indica el tipo de cola de mensajes no enviados que se ha de usar.</span><span class="sxs-lookup"><span data-stu-id="366db-116">An enumeration value that indicates the type of dead letter queue to use.</span></span>  
  
### <a name="durable"></a><span data-ttu-id="366db-117">Duradero</span><span class="sxs-lookup"><span data-stu-id="366db-117">Durable</span></span>  

 <span data-ttu-id="366db-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="366db-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="366db-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="366db-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="366db-120">Un valor que indica si los mensajes procesados por este enlace son duraderos o volátiles.</span><span class="sxs-lookup"><span data-stu-id="366db-120">A value that indicates whether the messages processed by this binding are durable or volatile.</span></span>  
  
### <a name="exactlyonce"></a><span data-ttu-id="366db-121">ExactlyOnce</span><span class="sxs-lookup"><span data-stu-id="366db-121">ExactlyOnce</span></span>  

 <span data-ttu-id="366db-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="366db-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="366db-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="366db-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="366db-124">Un valor booleano que indica si los mensajes procesados por este enlace se reciben solo una vez.</span><span class="sxs-lookup"><span data-stu-id="366db-124">A Boolean value that indicates whether messages processed by this binding are received exactly once.</span></span>  
  
### <a name="maxretrycycles"></a><span data-ttu-id="366db-125">MaxRetryCycles</span><span class="sxs-lookup"><span data-stu-id="366db-125">MaxRetryCycles</span></span>  

 <span data-ttu-id="366db-126">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="366db-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="366db-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="366db-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="366db-128">El número máximo de ciclos de reintento de entrega de mensajes a la aplicación receptora.</span><span class="sxs-lookup"><span data-stu-id="366db-128">The maximum number of retry cycles to attempt delivery of messages to the receiving application.</span></span>  
  
### <a name="receiveerrorhandling"></a><span data-ttu-id="366db-129">ReceiveErrorHandling</span><span class="sxs-lookup"><span data-stu-id="366db-129">ReceiveErrorHandling</span></span>  

 <span data-ttu-id="366db-130">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="366db-130">Data type: string</span></span>  
  
 <span data-ttu-id="366db-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="366db-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="366db-132">Los valores para el control de mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="366db-132">The settings for poison message handling.</span></span>  
  
### <a name="receiveretrycount"></a><span data-ttu-id="366db-133">ReceiveRetryCount</span><span class="sxs-lookup"><span data-stu-id="366db-133">ReceiveRetryCount</span></span>  

 <span data-ttu-id="366db-134">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="366db-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="366db-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="366db-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="366db-136">El número máximo de intentos de reintento inmediato en un mensaje que se lee desde la cola de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="366db-136">The maximum number of immediate retry attempts on a message that is read from the application queue.</span></span>  
  
### <a name="retrycycledelay"></a><span data-ttu-id="366db-137">RetryCycleDelay</span><span class="sxs-lookup"><span data-stu-id="366db-137">RetryCycleDelay</span></span>  

 <span data-ttu-id="366db-138">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="366db-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="366db-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="366db-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="366db-140">Un valor que indica el tiempo de retardo entre los ciclos de reintento al intentar entregar un mensaje que no se pudo entregar inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="366db-140">A value that indicates the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span>  
  
### <a name="timetolive"></a><span data-ttu-id="366db-141">timeToLive</span><span class="sxs-lookup"><span data-stu-id="366db-141">TimeToLive</span></span>  

 <span data-ttu-id="366db-142">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="366db-142">Data type: datetime</span></span>  
  
 <span data-ttu-id="366db-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="366db-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="366db-144">El intervalo de tiempo que indica cuánto tiempo pueden estar en la cola los mensajes procesados por este enlace antes de expirar.</span><span class="sxs-lookup"><span data-stu-id="366db-144">The interval of time that indicates how long the messages processed by this binding can be in the queue before they expire.</span></span>  
  
### <a name="usemsmqtracing"></a><span data-ttu-id="366db-145">UseMsmqTracing</span><span class="sxs-lookup"><span data-stu-id="366db-145">UseMsmqTracing</span></span>  

 <span data-ttu-id="366db-146">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="366db-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="366db-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="366db-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="366db-148">Un valor booleano que indica si los mensajes procesados por este enlace se deberían seguir paso a paso.</span><span class="sxs-lookup"><span data-stu-id="366db-148">A Boolean value that indicates whether messages processed by this binding should be traced.</span></span>  
  
### <a name="usesourcejournal"></a><span data-ttu-id="366db-149">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="366db-149">UseSourceJournal</span></span>  

 <span data-ttu-id="366db-150">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="366db-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="366db-151">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="366db-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="366db-152">Un valor booleano que indica si las copias de mensajes procesados por este enlace deberían almacenarse en la cola de diario de origen.</span><span class="sxs-lookup"><span data-stu-id="366db-152">A Boolean value that indicates whether copies of messages processed by this binding should be stored in the source journal queue.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="366db-153">Requisitos</span><span class="sxs-lookup"><span data-stu-id="366db-153">Requirements</span></span>  
  
|<span data-ttu-id="366db-154">MOF</span><span class="sxs-lookup"><span data-stu-id="366db-154">MOF</span></span>|<span data-ttu-id="366db-155">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="366db-155">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="366db-156">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="366db-156">Namespace</span></span>|<span data-ttu-id="366db-157">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="366db-157">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="366db-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="366db-158">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
