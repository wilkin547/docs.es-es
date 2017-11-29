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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bd784b470810e16b86ba7537b1f45681ac3e1ed1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="service"></a><span data-ttu-id="03856-102">Servicio</span><span class="sxs-lookup"><span data-stu-id="03856-102">Service</span></span>
<span data-ttu-id="03856-103">Servicio</span><span class="sxs-lookup"><span data-stu-id="03856-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03856-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03856-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="03856-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="03856-105">Methods</span></span>  
 <span data-ttu-id="03856-106">La clase Service no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="03856-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="03856-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="03856-107">Properties</span></span>  
 <span data-ttu-id="03856-108">La clase Service posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="03856-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="03856-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="03856-109">BaseAddresses</span></span>  
 <span data-ttu-id="03856-110">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="03856-110">Data type: string array</span></span>  
  
 <span data-ttu-id="03856-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="03856-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03856-112">Las direcciones base utilizadas por el servicio.</span><span class="sxs-lookup"><span data-stu-id="03856-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="03856-113">Comportamientos</span><span class="sxs-lookup"><span data-stu-id="03856-113">Behaviors</span></span>  
 <span data-ttu-id="03856-114">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="03856-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="03856-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="03856-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03856-116">Los comportamientos asociados a este servicio.</span><span class="sxs-lookup"><span data-stu-id="03856-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="03856-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="03856-117">ConfigurationName</span></span>  
 <span data-ttu-id="03856-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="03856-118">Data type: string</span></span>  
  
 <span data-ttu-id="03856-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="03856-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03856-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="03856-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="03856-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="03856-121">CounterInstanceName</span></span>  
 <span data-ttu-id="03856-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="03856-122">Data type: string</span></span>  
  
 <span data-ttu-id="03856-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="03856-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03856-124">Nombre de la instancia de los contadores de rendimiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="03856-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="03856-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="03856-125">DistinguishedName</span></span>  
 <span data-ttu-id="03856-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="03856-126">Data type: string</span></span>  
  
 <span data-ttu-id="03856-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="03856-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03856-128">Nombre de servicio en la dirección.</span><span class="sxs-lookup"><span data-stu-id="03856-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="03856-129">Extensiones</span><span class="sxs-lookup"><span data-stu-id="03856-129">Extensions</span></span>  
 <span data-ttu-id="03856-130">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="03856-130">Data type: string array</span></span>  
  
 <span data-ttu-id="03856-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="03856-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03856-132">Los contextos de instancia para las extensiones de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="03856-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="03856-133">Metadatos</span><span class="sxs-lookup"><span data-stu-id="03856-133">Metadata</span></span>  
 <span data-ttu-id="03856-134">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="03856-134">Data type: string array</span></span>  
  
 <span data-ttu-id="03856-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="03856-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03856-136">Los valores de metadatos de servicio.</span><span class="sxs-lookup"><span data-stu-id="03856-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="03856-137">Nombre</span><span class="sxs-lookup"><span data-stu-id="03856-137">Name</span></span>  
 <span data-ttu-id="03856-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="03856-138">Data type: string</span></span>  
  
 <span data-ttu-id="03856-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="03856-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03856-140">El nombre único de este servicio.</span><span class="sxs-lookup"><span data-stu-id="03856-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="03856-141">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="03856-141">Namespace</span></span>  
 <span data-ttu-id="03856-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="03856-142">Data type: string</span></span>  
  
 <span data-ttu-id="03856-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="03856-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03856-144">El espacio de nombres del servicio.</span><span class="sxs-lookup"><span data-stu-id="03856-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="03856-145">Abierto</span><span class="sxs-lookup"><span data-stu-id="03856-145">Opened</span></span>  
 <span data-ttu-id="03856-146">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="03856-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="03856-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="03856-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03856-148">El momento en el que se abrió el servicio.</span><span class="sxs-lookup"><span data-stu-id="03856-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="03856-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="03856-149">OutgoingChannels</span></span>  
 <span data-ttu-id="03856-150">Tipo de datos: matriz de canal</span><span class="sxs-lookup"><span data-stu-id="03856-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="03856-151">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="03856-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03856-152">Los canales que salen de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="03856-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="03856-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="03856-153">ProcessId</span></span>  
 <span data-ttu-id="03856-154">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="03856-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="03856-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="03856-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03856-156">El id. de proceso que hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="03856-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03856-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03856-157">Requirements</span></span>  
  
|<span data-ttu-id="03856-158">MOF</span><span class="sxs-lookup"><span data-stu-id="03856-158">MOF</span></span>|<span data-ttu-id="03856-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="03856-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="03856-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="03856-160">Namespace</span></span>|<span data-ttu-id="03856-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="03856-161">Defined in root\ServiceModel</span></span>|
