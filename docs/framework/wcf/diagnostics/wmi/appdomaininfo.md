---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: 0b7f8aadbd9a9dfcdd33fc65be3a5a41ea95f5be
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50170229"
---
# <a name="appdomaininfo"></a><span data-ttu-id="1f8fb-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="1f8fb-102">AppDomainInfo</span></span>
<span data-ttu-id="1f8fb-103">Información del dominio de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1f8fb-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f8fb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f8fb-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="1f8fb-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1f8fb-105">Methods</span></span>  
 <span data-ttu-id="1f8fb-106">La clase AppDomainInfo no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="1f8fb-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1f8fb-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1f8fb-107">Properties</span></span>  
 <span data-ttu-id="1f8fb-108">La clase AppDomainInfo tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f8fb-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="1f8fb-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="1f8fb-109">AppDomainId</span></span>  
 <span data-ttu-id="1f8fb-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="1f8fb-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="1f8fb-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1f8fb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f8fb-112">El id. de appdomain.</span><span class="sxs-lookup"><span data-stu-id="1f8fb-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="1f8fb-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="1f8fb-113">IsDefault</span></span>  
 <span data-ttu-id="1f8fb-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="1f8fb-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="1f8fb-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1f8fb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f8fb-116">Indica si appdomain es el appdomain predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1f8fb-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="1f8fb-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="1f8fb-117">LogMalformedMessages</span></span>  
 <span data-ttu-id="1f8fb-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="1f8fb-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="1f8fb-119">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="1f8fb-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="1f8fb-120">Valor booleano que especifica si se registran los mensajes con formato erróneo.</span><span class="sxs-lookup"><span data-stu-id="1f8fb-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="1f8fb-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="1f8fb-121">LogMessagesAtServiceLevel</span></span>  
 <span data-ttu-id="1f8fb-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="1f8fb-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="1f8fb-123">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="1f8fb-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="1f8fb-124">Valor booleano que especifica si los mensajes se siguen en el nivel de servicio (antes del cifrado y las transformaciones relacionadas con transporte).</span><span class="sxs-lookup"><span data-stu-id="1f8fb-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="1f8fb-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="1f8fb-125">LogMessagesAtTransportLevel</span></span>  
 <span data-ttu-id="1f8fb-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="1f8fb-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="1f8fb-127">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="1f8fb-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="1f8fb-128">Valor booleano que especifica si los mensajes se siguen en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="1f8fb-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="1f8fb-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="1f8fb-129">MessageLoggingTraceListeners</span></span>  
 <span data-ttu-id="1f8fb-130">Matriz TraceListener de tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1f8fb-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="1f8fb-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1f8fb-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f8fb-132">Los agentes de escucha de seguimiento de colección que escuchan el origen de seguimiento de System.Wmi.MessageLogging.</span><span class="sxs-lookup"><span data-stu-id="1f8fb-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="1f8fb-133">nombre</span><span class="sxs-lookup"><span data-stu-id="1f8fb-133">Name</span></span>  
 <span data-ttu-id="1f8fb-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1f8fb-134">Data type: string</span></span>  
  
 <span data-ttu-id="1f8fb-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1f8fb-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f8fb-136">El nombre de appdomain.</span><span class="sxs-lookup"><span data-stu-id="1f8fb-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="1f8fb-137">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="1f8fb-137">PerformanceCounters</span></span>  
 <span data-ttu-id="1f8fb-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1f8fb-138">Data type: string</span></span>  
  
 <span data-ttu-id="1f8fb-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1f8fb-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f8fb-140">El ámbito de contadores de rendimiento activos en el appdomain.</span><span class="sxs-lookup"><span data-stu-id="1f8fb-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="1f8fb-141">ProcessId</span><span class="sxs-lookup"><span data-stu-id="1f8fb-141">ProcessId</span></span>  
 <span data-ttu-id="1f8fb-142">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="1f8fb-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="1f8fb-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1f8fb-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f8fb-144">El id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="1f8fb-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="1f8fb-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="1f8fb-145">ServiceConfigPath</span></span>  
 <span data-ttu-id="1f8fb-146">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1f8fb-146">Data type: string</span></span>  
  
 <span data-ttu-id="1f8fb-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1f8fb-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f8fb-148">Ruta de acceso a la configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="1f8fb-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="1f8fb-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="1f8fb-149">TraceLevel</span></span>  
 <span data-ttu-id="1f8fb-150">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1f8fb-150">Data type: string</span></span>  
  
 <span data-ttu-id="1f8fb-151">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="1f8fb-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="1f8fb-152">El nivel de seguimiento del origen de seguimiento de System.Wmi.</span><span class="sxs-lookup"><span data-stu-id="1f8fb-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="1f8fb-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="1f8fb-153">ServiceModelTraceListeners</span></span>  
 <span data-ttu-id="1f8fb-154">Matriz TraceListener de tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1f8fb-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="1f8fb-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1f8fb-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f8fb-156">Una colección de agentes de escucha del origen de seguimiento de System.ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="1f8fb-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f8fb-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f8fb-157">Requirements</span></span>  
  
|<span data-ttu-id="1f8fb-158">MOF</span><span class="sxs-lookup"><span data-stu-id="1f8fb-158">MOF</span></span>|<span data-ttu-id="1f8fb-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1f8fb-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1f8fb-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="1f8fb-160">Namespace</span></span>|<span data-ttu-id="1f8fb-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1f8fb-161">Defined in root\ServiceModel</span></span>|
