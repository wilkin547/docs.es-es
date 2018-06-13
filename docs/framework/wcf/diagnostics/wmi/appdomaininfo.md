---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: 7189448a930298837089cf3ac2743cb7e073ae02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486986"
---
# <a name="appdomaininfo"></a><span data-ttu-id="d1104-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="d1104-102">AppDomainInfo</span></span>
<span data-ttu-id="d1104-103">Información del dominio de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="d1104-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1104-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1104-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="d1104-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d1104-105">Methods</span></span>  
 <span data-ttu-id="d1104-106">La clase AppDomainInfo no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="d1104-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d1104-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d1104-107">Properties</span></span>  
 <span data-ttu-id="d1104-108">La clase AppDomainInfo tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="d1104-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="d1104-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="d1104-109">AppDomainId</span></span>  
 <span data-ttu-id="d1104-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="d1104-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="d1104-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d1104-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1104-112">El id. de appdomain.</span><span class="sxs-lookup"><span data-stu-id="d1104-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="d1104-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="d1104-113">IsDefault</span></span>  
 <span data-ttu-id="d1104-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="d1104-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="d1104-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d1104-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1104-116">Indica si appdomain es el appdomain predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d1104-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="d1104-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="d1104-117">LogMalformedMessages</span></span>  
 <span data-ttu-id="d1104-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="d1104-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="d1104-119">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="d1104-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="d1104-120">Valor booleano que especifica si se registran los mensajes con formato erróneo.</span><span class="sxs-lookup"><span data-stu-id="d1104-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="d1104-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="d1104-121">LogMessagesAtServiceLevel</span></span>  
 <span data-ttu-id="d1104-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="d1104-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="d1104-123">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="d1104-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="d1104-124">Valor booleano que especifica si los mensajes se siguen en el nivel de servicio (antes del cifrado y las transformaciones relacionadas con transporte).</span><span class="sxs-lookup"><span data-stu-id="d1104-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="d1104-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="d1104-125">LogMessagesAtTransportLevel</span></span>  
 <span data-ttu-id="d1104-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="d1104-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="d1104-127">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="d1104-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="d1104-128">Valor booleano que especifica si los mensajes se siguen en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="d1104-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="d1104-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="d1104-129">MessageLoggingTraceListeners</span></span>  
 <span data-ttu-id="d1104-130">Matriz TraceListener de tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d1104-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="d1104-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d1104-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1104-132">Los agentes de escucha de seguimiento de colección que escuchan el origen de seguimiento de System.Wmi.MessageLogging.</span><span class="sxs-lookup"><span data-stu-id="d1104-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="d1104-133">nombre</span><span class="sxs-lookup"><span data-stu-id="d1104-133">Name</span></span>  
 <span data-ttu-id="d1104-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d1104-134">Data type: string</span></span>  
  
 <span data-ttu-id="d1104-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d1104-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1104-136">El nombre de appdomain.</span><span class="sxs-lookup"><span data-stu-id="d1104-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="d1104-137">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="d1104-137">PerformanceCounters</span></span>  
 <span data-ttu-id="d1104-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d1104-138">Data type: string</span></span>  
  
 <span data-ttu-id="d1104-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d1104-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1104-140">El ámbito de contadores de rendimiento activos en el appdomain.</span><span class="sxs-lookup"><span data-stu-id="d1104-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="d1104-141">ProcessId</span><span class="sxs-lookup"><span data-stu-id="d1104-141">ProcessId</span></span>  
 <span data-ttu-id="d1104-142">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="d1104-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="d1104-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d1104-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1104-144">El id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="d1104-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="d1104-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="d1104-145">ServiceConfigPath</span></span>  
 <span data-ttu-id="d1104-146">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d1104-146">Data type: string</span></span>  
  
 <span data-ttu-id="d1104-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d1104-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1104-148">Ruta de acceso a la configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="d1104-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="d1104-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="d1104-149">TraceLevel</span></span>  
 <span data-ttu-id="d1104-150">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d1104-150">Data type: string</span></span>  
  
 <span data-ttu-id="d1104-151">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="d1104-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="d1104-152">El nivel de seguimiento del origen de seguimiento de System.Wmi.</span><span class="sxs-lookup"><span data-stu-id="d1104-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="d1104-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="d1104-153">ServiceModelTraceListeners</span></span>  
 <span data-ttu-id="d1104-154">Matriz TraceListener de tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d1104-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="d1104-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d1104-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1104-156">Una colección de agentes de escucha del origen de seguimiento de System.ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="d1104-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1104-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1104-157">Requirements</span></span>  
  
|<span data-ttu-id="d1104-158">MOF</span><span class="sxs-lookup"><span data-stu-id="d1104-158">MOF</span></span>|<span data-ttu-id="d1104-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d1104-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d1104-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="d1104-160">Namespace</span></span>|<span data-ttu-id="d1104-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d1104-161">Defined in root\ServiceModel</span></span>|
