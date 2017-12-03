---
title: Servicio
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 027366e7bf7abd285ef65da2040514b4b9908213
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="service"></a><span data-ttu-id="e8008-102">Servicio</span><span class="sxs-lookup"><span data-stu-id="e8008-102">Service</span></span>
<span data-ttu-id="e8008-103">Servicio</span><span class="sxs-lookup"><span data-stu-id="e8008-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8008-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8008-104">Syntax</span></span>  
  
```  
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e8008-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e8008-105">Methods</span></span>  
 <span data-ttu-id="e8008-106">La clase Service no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="e8008-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e8008-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e8008-107">Properties</span></span>  
 <span data-ttu-id="e8008-108">La clase Service posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="e8008-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="e8008-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="e8008-109">BaseAddresses</span></span>  
 <span data-ttu-id="e8008-110">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="e8008-110">Data type: string array</span></span>  
  
 <span data-ttu-id="e8008-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e8008-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8008-112">Las direcciones base utilizadas por el servicio.</span><span class="sxs-lookup"><span data-stu-id="e8008-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="e8008-113">Comportamientos</span><span class="sxs-lookup"><span data-stu-id="e8008-113">Behaviors</span></span>  
 <span data-ttu-id="e8008-114">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="e8008-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="e8008-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e8008-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8008-116">Los comportamientos asociados a este servicio.</span><span class="sxs-lookup"><span data-stu-id="e8008-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="e8008-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="e8008-117">ConfigurationName</span></span>  
 <span data-ttu-id="e8008-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e8008-118">Data type: string</span></span>  
  
 <span data-ttu-id="e8008-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e8008-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8008-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="e8008-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="e8008-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="e8008-121">CounterInstanceName</span></span>  
 <span data-ttu-id="e8008-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e8008-122">Data type: string</span></span>  
  
 <span data-ttu-id="e8008-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e8008-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8008-124">Nombre de la instancia de los contadores de rendimiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="e8008-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="e8008-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="e8008-125">DistinguishedName</span></span>  
 <span data-ttu-id="e8008-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e8008-126">Data type: string</span></span>  
  
 <span data-ttu-id="e8008-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e8008-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8008-128">Nombre de servicio en la dirección.</span><span class="sxs-lookup"><span data-stu-id="e8008-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="e8008-129">Extensiones</span><span class="sxs-lookup"><span data-stu-id="e8008-129">Extensions</span></span>  
 <span data-ttu-id="e8008-130">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="e8008-130">Data type: string array</span></span>  
  
 <span data-ttu-id="e8008-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e8008-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8008-132">Los contextos de instancia para las extensiones de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="e8008-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="e8008-133">Metadatos</span><span class="sxs-lookup"><span data-stu-id="e8008-133">Metadata</span></span>  
 <span data-ttu-id="e8008-134">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="e8008-134">Data type: string array</span></span>  
  
 <span data-ttu-id="e8008-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e8008-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8008-136">Los valores de metadatos de servicio.</span><span class="sxs-lookup"><span data-stu-id="e8008-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="e8008-137">Nombre</span><span class="sxs-lookup"><span data-stu-id="e8008-137">Name</span></span>  
 <span data-ttu-id="e8008-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e8008-138">Data type: string</span></span>  
  
 <span data-ttu-id="e8008-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e8008-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8008-140">El nombre único de este servicio.</span><span class="sxs-lookup"><span data-stu-id="e8008-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="e8008-141">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e8008-141">Namespace</span></span>  
 <span data-ttu-id="e8008-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e8008-142">Data type: string</span></span>  
  
 <span data-ttu-id="e8008-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e8008-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8008-144">El espacio de nombres del servicio.</span><span class="sxs-lookup"><span data-stu-id="e8008-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="e8008-145">Abierto</span><span class="sxs-lookup"><span data-stu-id="e8008-145">Opened</span></span>  
 <span data-ttu-id="e8008-146">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="e8008-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="e8008-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e8008-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8008-148">El momento en el que se abrió el servicio.</span><span class="sxs-lookup"><span data-stu-id="e8008-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="e8008-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="e8008-149">OutgoingChannels</span></span>  
 <span data-ttu-id="e8008-150">Tipo de datos: matriz de canal</span><span class="sxs-lookup"><span data-stu-id="e8008-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="e8008-151">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e8008-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8008-152">Los canales que salen de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="e8008-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="e8008-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="e8008-153">ProcessId</span></span>  
 <span data-ttu-id="e8008-154">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="e8008-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="e8008-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e8008-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8008-156">El id. de proceso que hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="e8008-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8008-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8008-157">Requirements</span></span>  
  
|<span data-ttu-id="e8008-158">MOF</span><span class="sxs-lookup"><span data-stu-id="e8008-158">MOF</span></span>|<span data-ttu-id="e8008-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e8008-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e8008-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e8008-160">Namespace</span></span>|<span data-ttu-id="e8008-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e8008-161">Defined in root\ServiceModel</span></span>|
