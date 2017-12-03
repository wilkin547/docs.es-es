---
title: AppDomainInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 76fee9673514287dd120a215fc843e4d995e68c0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="appdomaininfo"></a><span data-ttu-id="b4bbd-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="b4bbd-102">AppDomainInfo</span></span>
<span data-ttu-id="b4bbd-103">Información del dominio de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b4bbd-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4bbd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4bbd-104">Syntax</span></span>  
  
```  
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b4bbd-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b4bbd-105">Methods</span></span>  
 <span data-ttu-id="b4bbd-106">La clase AppDomainInfo no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b4bbd-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b4bbd-107">Properties</span></span>  
 <span data-ttu-id="b4bbd-108">La clase AppDomainInfo tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="b4bbd-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="b4bbd-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="b4bbd-109">AppDomainId</span></span>  
 <span data-ttu-id="b4bbd-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="b4bbd-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="b4bbd-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4bbd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4bbd-112">El id. de appdomain.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="b4bbd-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="b4bbd-113">IsDefault</span></span>  
 <span data-ttu-id="b4bbd-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="b4bbd-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="b4bbd-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4bbd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4bbd-116">Indica si appdomain es el appdomain predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="b4bbd-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="b4bbd-117">LogMalformedMessages</span></span>  
 <span data-ttu-id="b4bbd-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="b4bbd-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="b4bbd-119">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="b4bbd-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="b4bbd-120">Valor booleano que especifica si se registran los mensajes con formato erróneo.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="b4bbd-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="b4bbd-121">LogMessagesAtServiceLevel</span></span>  
 <span data-ttu-id="b4bbd-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="b4bbd-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="b4bbd-123">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="b4bbd-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="b4bbd-124">Valor booleano que especifica si los mensajes se siguen en el nivel de servicio (antes del cifrado y las transformaciones relacionadas con transporte).</span><span class="sxs-lookup"><span data-stu-id="b4bbd-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="b4bbd-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="b4bbd-125">LogMessagesAtTransportLevel</span></span>  
 <span data-ttu-id="b4bbd-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="b4bbd-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="b4bbd-127">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="b4bbd-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="b4bbd-128">Valor booleano que especifica si los mensajes se siguen en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="b4bbd-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="b4bbd-129">MessageLoggingTraceListeners</span></span>  
 <span data-ttu-id="b4bbd-130">Matriz TraceListener de tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b4bbd-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="b4bbd-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4bbd-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4bbd-132">Los agentes de escucha de seguimiento de colección que escuchan el origen de seguimiento de System.Wmi.MessageLogging.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="b4bbd-133">Nombre</span><span class="sxs-lookup"><span data-stu-id="b4bbd-133">Name</span></span>  
 <span data-ttu-id="b4bbd-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b4bbd-134">Data type: string</span></span>  
  
 <span data-ttu-id="b4bbd-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4bbd-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4bbd-136">El nombre de appdomain.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="b4bbd-137">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="b4bbd-137">PerformanceCounters</span></span>  
 <span data-ttu-id="b4bbd-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b4bbd-138">Data type: string</span></span>  
  
 <span data-ttu-id="b4bbd-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4bbd-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4bbd-140">El ámbito de contadores de rendimiento activos en el appdomain.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="b4bbd-141">ProcessId</span><span class="sxs-lookup"><span data-stu-id="b4bbd-141">ProcessId</span></span>  
 <span data-ttu-id="b4bbd-142">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="b4bbd-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="b4bbd-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4bbd-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4bbd-144">El id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="b4bbd-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="b4bbd-145">ServiceConfigPath</span></span>  
 <span data-ttu-id="b4bbd-146">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b4bbd-146">Data type: string</span></span>  
  
 <span data-ttu-id="b4bbd-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4bbd-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4bbd-148">Ruta de acceso a la configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="b4bbd-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="b4bbd-149">TraceLevel</span></span>  
 <span data-ttu-id="b4bbd-150">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b4bbd-150">Data type: string</span></span>  
  
 <span data-ttu-id="b4bbd-151">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="b4bbd-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="b4bbd-152">El nivel de seguimiento del origen de seguimiento de System.Wmi.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="b4bbd-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="b4bbd-153">ServiceModelTraceListeners</span></span>  
 <span data-ttu-id="b4bbd-154">Matriz TraceListener de tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b4bbd-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="b4bbd-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4bbd-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4bbd-156">Una colección de agentes de escucha del origen de seguimiento de System.ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4bbd-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4bbd-157">Requirements</span></span>  
  
|<span data-ttu-id="b4bbd-158">MOF</span><span class="sxs-lookup"><span data-stu-id="b4bbd-158">MOF</span></span>|<span data-ttu-id="b4bbd-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b4bbd-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b4bbd-160">Namespace</span></span>|<span data-ttu-id="b4bbd-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b4bbd-161">Defined in root\ServiceModel</span></span>|
