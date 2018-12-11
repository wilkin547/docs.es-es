---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: 0b7f8aadbd9a9dfcdd33fc65be3a5a41ea95f5be
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127087"
---
# <a name="appdomaininfo"></a><span data-ttu-id="94e50-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="94e50-102">AppDomainInfo</span></span>
<span data-ttu-id="94e50-103">Información del dominio de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="94e50-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94e50-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94e50-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="94e50-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="94e50-105">Methods</span></span>  
 <span data-ttu-id="94e50-106">La clase AppDomainInfo no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="94e50-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="94e50-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="94e50-107">Properties</span></span>  
 <span data-ttu-id="94e50-108">La clase AppDomainInfo tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="94e50-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="94e50-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="94e50-109">AppDomainId</span></span>  
 <span data-ttu-id="94e50-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="94e50-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="94e50-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="94e50-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94e50-112">El id. de appdomain.</span><span class="sxs-lookup"><span data-stu-id="94e50-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="94e50-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="94e50-113">IsDefault</span></span>  
 <span data-ttu-id="94e50-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="94e50-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="94e50-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="94e50-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94e50-116">Indica si appdomain es el appdomain predeterminado.</span><span class="sxs-lookup"><span data-stu-id="94e50-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="94e50-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="94e50-117">LogMalformedMessages</span></span>  
 <span data-ttu-id="94e50-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="94e50-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="94e50-119">Tipo de acceso: Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="94e50-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="94e50-120">Valor booleano que especifica si se registran los mensajes con formato erróneo.</span><span class="sxs-lookup"><span data-stu-id="94e50-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="94e50-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="94e50-121">LogMessagesAtServiceLevel</span></span>  
 <span data-ttu-id="94e50-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="94e50-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="94e50-123">Tipo de acceso: Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="94e50-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="94e50-124">Valor booleano que especifica si los mensajes se siguen en el nivel de servicio (antes del cifrado y las transformaciones relacionadas con transporte).</span><span class="sxs-lookup"><span data-stu-id="94e50-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="94e50-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="94e50-125">LogMessagesAtTransportLevel</span></span>  
 <span data-ttu-id="94e50-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="94e50-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="94e50-127">Tipo de acceso: Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="94e50-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="94e50-128">Valor booleano que especifica si los mensajes se siguen en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="94e50-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="94e50-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="94e50-129">MessageLoggingTraceListeners</span></span>  
 <span data-ttu-id="94e50-130">Tipo de datos: Matriz TraceListener</span><span class="sxs-lookup"><span data-stu-id="94e50-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="94e50-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="94e50-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94e50-132">Los agentes de escucha de seguimiento de colección que escuchan el origen de seguimiento de System.Wmi.MessageLogging.</span><span class="sxs-lookup"><span data-stu-id="94e50-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="94e50-133">nombre</span><span class="sxs-lookup"><span data-stu-id="94e50-133">Name</span></span>  
 <span data-ttu-id="94e50-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="94e50-134">Data type: string</span></span>  
  
 <span data-ttu-id="94e50-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="94e50-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94e50-136">El nombre de appdomain.</span><span class="sxs-lookup"><span data-stu-id="94e50-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="94e50-137">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="94e50-137">PerformanceCounters</span></span>  
 <span data-ttu-id="94e50-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="94e50-138">Data type: string</span></span>  
  
 <span data-ttu-id="94e50-139">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="94e50-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94e50-140">El ámbito de contadores de rendimiento activos en el appdomain.</span><span class="sxs-lookup"><span data-stu-id="94e50-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="94e50-141">ProcessId</span><span class="sxs-lookup"><span data-stu-id="94e50-141">ProcessId</span></span>  
 <span data-ttu-id="94e50-142">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="94e50-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="94e50-143">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="94e50-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94e50-144">El id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="94e50-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="94e50-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="94e50-145">ServiceConfigPath</span></span>  
 <span data-ttu-id="94e50-146">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="94e50-146">Data type: string</span></span>  
  
 <span data-ttu-id="94e50-147">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="94e50-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94e50-148">Ruta de acceso a la configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="94e50-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="94e50-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="94e50-149">TraceLevel</span></span>  
 <span data-ttu-id="94e50-150">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="94e50-150">Data type: string</span></span>  
  
 <span data-ttu-id="94e50-151">Tipo de acceso: Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="94e50-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="94e50-152">El nivel de seguimiento del origen de seguimiento de System.Wmi.</span><span class="sxs-lookup"><span data-stu-id="94e50-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="94e50-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="94e50-153">ServiceModelTraceListeners</span></span>  
 <span data-ttu-id="94e50-154">Tipo de datos: Matriz TraceListener</span><span class="sxs-lookup"><span data-stu-id="94e50-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="94e50-155">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="94e50-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94e50-156">Una colección de agentes de escucha del origen de seguimiento de System.ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="94e50-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94e50-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94e50-157">Requirements</span></span>  
  
|<span data-ttu-id="94e50-158">MOF</span><span class="sxs-lookup"><span data-stu-id="94e50-158">MOF</span></span>|<span data-ttu-id="94e50-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="94e50-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="94e50-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="94e50-160">Namespace</span></span>|<span data-ttu-id="94e50-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="94e50-161">Defined in root\ServiceModel</span></span>|
