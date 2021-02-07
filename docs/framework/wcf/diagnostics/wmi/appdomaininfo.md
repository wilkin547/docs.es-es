---
description: 'Más información acerca de: AppDomainInfo'
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: 1e527f2a25c48a3bf35d974e3ac192d937a8a86e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757974"
---
# <a name="appdomaininfo"></a><span data-ttu-id="88562-103">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="88562-103">AppDomainInfo</span></span>

<span data-ttu-id="88562-104">Información del dominio de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="88562-104">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88562-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88562-105">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="88562-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="88562-106">Methods</span></span>  

 <span data-ttu-id="88562-107">La clase AppDomainInfo no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="88562-107">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="88562-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="88562-108">Properties</span></span>  

 <span data-ttu-id="88562-109">La clase AppDomainInfo tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="88562-109">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="88562-110">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="88562-110">AppDomainId</span></span>  

 <span data-ttu-id="88562-111">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="88562-111">Data type: sint32</span></span>  
  
 <span data-ttu-id="88562-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="88562-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88562-113">El id. de appdomain.</span><span class="sxs-lookup"><span data-stu-id="88562-113">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="88562-114">IsDefault</span><span class="sxs-lookup"><span data-stu-id="88562-114">IsDefault</span></span>  

 <span data-ttu-id="88562-115">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="88562-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="88562-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="88562-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88562-117">Indica si appdomain es el appdomain predeterminado.</span><span class="sxs-lookup"><span data-stu-id="88562-117">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="88562-118">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="88562-118">LogMalformedMessages</span></span>  

 <span data-ttu-id="88562-119">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="88562-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="88562-120">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="88562-120">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="88562-121">Valor booleano que especifica si se registran los mensajes con formato erróneo.</span><span class="sxs-lookup"><span data-stu-id="88562-121">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="88562-122">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="88562-122">LogMessagesAtServiceLevel</span></span>  

 <span data-ttu-id="88562-123">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="88562-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="88562-124">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="88562-124">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="88562-125">Valor booleano que especifica si los mensajes se siguen en el nivel de servicio (antes del cifrado y las transformaciones relacionadas con transporte).</span><span class="sxs-lookup"><span data-stu-id="88562-125">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="88562-126">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="88562-126">LogMessagesAtTransportLevel</span></span>  

 <span data-ttu-id="88562-127">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="88562-127">Data type: boolean</span></span>  
  
 <span data-ttu-id="88562-128">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="88562-128">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="88562-129">Valor booleano que especifica si los mensajes se siguen en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="88562-129">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="88562-130">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="88562-130">MessageLoggingTraceListeners</span></span>  

 <span data-ttu-id="88562-131">Matriz TraceListener de tipo de datos</span><span class="sxs-lookup"><span data-stu-id="88562-131">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="88562-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="88562-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88562-133">Los agentes de escucha de seguimiento de colección que escuchan el origen de seguimiento de System.Wmi.MessageLogging.</span><span class="sxs-lookup"><span data-stu-id="88562-133">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="88562-134">Nombre</span><span class="sxs-lookup"><span data-stu-id="88562-134">Name</span></span>  

 <span data-ttu-id="88562-135">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="88562-135">Data type: string</span></span>  
  
 <span data-ttu-id="88562-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="88562-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88562-137">El nombre de appdomain.</span><span class="sxs-lookup"><span data-stu-id="88562-137">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="88562-138">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="88562-138">PerformanceCounters</span></span>  

 <span data-ttu-id="88562-139">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="88562-139">Data type: string</span></span>  
  
 <span data-ttu-id="88562-140">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="88562-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88562-141">El ámbito de contadores de rendimiento activos en el appdomain.</span><span class="sxs-lookup"><span data-stu-id="88562-141">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="88562-142">ProcessId</span><span class="sxs-lookup"><span data-stu-id="88562-142">ProcessId</span></span>  

 <span data-ttu-id="88562-143">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="88562-143">Data type: sint32</span></span>  
  
 <span data-ttu-id="88562-144">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="88562-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88562-145">El id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="88562-145">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="88562-146">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="88562-146">ServiceConfigPath</span></span>  

 <span data-ttu-id="88562-147">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="88562-147">Data type: string</span></span>  
  
 <span data-ttu-id="88562-148">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="88562-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88562-149">Ruta de acceso a la configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="88562-149">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="88562-150">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="88562-150">TraceLevel</span></span>  

 <span data-ttu-id="88562-151">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="88562-151">Data type: string</span></span>  
  
 <span data-ttu-id="88562-152">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="88562-152">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="88562-153">El nivel de seguimiento del origen de seguimiento de System.Wmi.</span><span class="sxs-lookup"><span data-stu-id="88562-153">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="88562-154">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="88562-154">ServiceModelTraceListeners</span></span>  

 <span data-ttu-id="88562-155">Matriz TraceListener de tipo de datos</span><span class="sxs-lookup"><span data-stu-id="88562-155">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="88562-156">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="88562-156">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88562-157">Una colección de agentes de escucha del origen de seguimiento de System.ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="88562-157">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88562-158">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88562-158">Requirements</span></span>  
  
|<span data-ttu-id="88562-159">MOF</span><span class="sxs-lookup"><span data-stu-id="88562-159">MOF</span></span>|<span data-ttu-id="88562-160">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="88562-160">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="88562-161">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="88562-161">Namespace</span></span>|<span data-ttu-id="88562-162">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="88562-162">Defined in root\ServiceModel</span></span>|
