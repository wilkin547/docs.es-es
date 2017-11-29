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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 97818cf1fc6fa1c59b8b0eeaab69a73b21360151
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="appdomaininfo"></a><span data-ttu-id="610e1-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="610e1-102">AppDomainInfo</span></span>
<span data-ttu-id="610e1-103">Información del dominio de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="610e1-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="610e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="610e1-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="610e1-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="610e1-105">Methods</span></span>  
 <span data-ttu-id="610e1-106">La clase AppDomainInfo no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="610e1-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="610e1-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="610e1-107">Properties</span></span>  
 <span data-ttu-id="610e1-108">La clase AppDomainInfo tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="610e1-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="610e1-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="610e1-109">AppDomainId</span></span>  
 <span data-ttu-id="610e1-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="610e1-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="610e1-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="610e1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="610e1-112">El id. de appdomain.</span><span class="sxs-lookup"><span data-stu-id="610e1-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="610e1-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="610e1-113">IsDefault</span></span>  
 <span data-ttu-id="610e1-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="610e1-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="610e1-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="610e1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="610e1-116">Indica si appdomain es el appdomain predeterminado.</span><span class="sxs-lookup"><span data-stu-id="610e1-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="610e1-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="610e1-117">LogMalformedMessages</span></span>  
 <span data-ttu-id="610e1-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="610e1-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="610e1-119">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="610e1-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="610e1-120">Valor booleano que especifica si se registran los mensajes con formato erróneo.</span><span class="sxs-lookup"><span data-stu-id="610e1-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="610e1-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="610e1-121">LogMessagesAtServiceLevel</span></span>  
 <span data-ttu-id="610e1-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="610e1-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="610e1-123">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="610e1-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="610e1-124">Valor booleano que especifica si los mensajes se siguen en el nivel de servicio (antes del cifrado y las transformaciones relacionadas con transporte).</span><span class="sxs-lookup"><span data-stu-id="610e1-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="610e1-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="610e1-125">LogMessagesAtTransportLevel</span></span>  
 <span data-ttu-id="610e1-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="610e1-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="610e1-127">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="610e1-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="610e1-128">Valor booleano que especifica si los mensajes se siguen en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="610e1-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="610e1-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="610e1-129">MessageLoggingTraceListeners</span></span>  
 <span data-ttu-id="610e1-130">Matriz TraceListener de tipo de datos</span><span class="sxs-lookup"><span data-stu-id="610e1-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="610e1-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="610e1-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="610e1-132">Los agentes de escucha de seguimiento de colección que escuchan el origen de seguimiento de System.Wmi.MessageLogging.</span><span class="sxs-lookup"><span data-stu-id="610e1-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="610e1-133">Nombre</span><span class="sxs-lookup"><span data-stu-id="610e1-133">Name</span></span>  
 <span data-ttu-id="610e1-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="610e1-134">Data type: string</span></span>  
  
 <span data-ttu-id="610e1-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="610e1-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="610e1-136">El nombre de appdomain.</span><span class="sxs-lookup"><span data-stu-id="610e1-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="610e1-137">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="610e1-137">PerformanceCounters</span></span>  
 <span data-ttu-id="610e1-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="610e1-138">Data type: string</span></span>  
  
 <span data-ttu-id="610e1-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="610e1-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="610e1-140">El ámbito de contadores de rendimiento activos en el appdomain.</span><span class="sxs-lookup"><span data-stu-id="610e1-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="610e1-141">ProcessId</span><span class="sxs-lookup"><span data-stu-id="610e1-141">ProcessId</span></span>  
 <span data-ttu-id="610e1-142">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="610e1-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="610e1-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="610e1-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="610e1-144">El id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="610e1-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="610e1-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="610e1-145">ServiceConfigPath</span></span>  
 <span data-ttu-id="610e1-146">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="610e1-146">Data type: string</span></span>  
  
 <span data-ttu-id="610e1-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="610e1-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="610e1-148">Ruta de acceso a la configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="610e1-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="610e1-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="610e1-149">TraceLevel</span></span>  
 <span data-ttu-id="610e1-150">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="610e1-150">Data type: string</span></span>  
  
 <span data-ttu-id="610e1-151">Tipo de acceso: lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="610e1-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="610e1-152">El nivel de seguimiento del origen de seguimiento de System.Wmi.</span><span class="sxs-lookup"><span data-stu-id="610e1-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="610e1-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="610e1-153">ServiceModelTraceListeners</span></span>  
 <span data-ttu-id="610e1-154">Matriz TraceListener de tipo de datos</span><span class="sxs-lookup"><span data-stu-id="610e1-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="610e1-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="610e1-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="610e1-156">Una colección de agentes de escucha del origen de seguimiento de System.ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="610e1-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="610e1-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="610e1-157">Requirements</span></span>  
  
|<span data-ttu-id="610e1-158">MOF</span><span class="sxs-lookup"><span data-stu-id="610e1-158">MOF</span></span>|<span data-ttu-id="610e1-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="610e1-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="610e1-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="610e1-160">Namespace</span></span>|<span data-ttu-id="610e1-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="610e1-161">Defined in root\ServiceModel</span></span>|
