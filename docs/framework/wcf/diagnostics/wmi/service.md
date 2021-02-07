---
description: 'Más información acerca de: servicio'
title: Servicio
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: e66f9a23f8c182327899904c26ff6a6368b9bdc6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715631"
---
# <a name="service"></a><span data-ttu-id="b4069-103">Servicio</span><span class="sxs-lookup"><span data-stu-id="b4069-103">Service</span></span>

<span data-ttu-id="b4069-104">Servicio</span><span class="sxs-lookup"><span data-stu-id="b4069-104">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4069-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4069-105">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="b4069-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="b4069-106">Methods</span></span>  

 <span data-ttu-id="b4069-107">La clase Service no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="b4069-107">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b4069-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b4069-108">Properties</span></span>  

 <span data-ttu-id="b4069-109">La clase Service posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b4069-109">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="b4069-110">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="b4069-110">BaseAddresses</span></span>  

 <span data-ttu-id="b4069-111">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="b4069-111">Data type: string array</span></span>  
  
 <span data-ttu-id="b4069-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4069-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4069-113">Las direcciones base utilizadas por el servicio.</span><span class="sxs-lookup"><span data-stu-id="b4069-113">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="b4069-114">Comportamientos</span><span class="sxs-lookup"><span data-stu-id="b4069-114">Behaviors</span></span>  

 <span data-ttu-id="b4069-115">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="b4069-115">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="b4069-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4069-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4069-117">Los comportamientos asociados a este servicio.</span><span class="sxs-lookup"><span data-stu-id="b4069-117">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="b4069-118">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="b4069-118">ConfigurationName</span></span>  

 <span data-ttu-id="b4069-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b4069-119">Data type: string</span></span>  
  
 <span data-ttu-id="b4069-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4069-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4069-121">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="b4069-121">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="b4069-122">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="b4069-122">CounterInstanceName</span></span>  

 <span data-ttu-id="b4069-123">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b4069-123">Data type: string</span></span>  
  
 <span data-ttu-id="b4069-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4069-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4069-125">Nombre de la instancia de los contadores de rendimiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="b4069-125">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="b4069-126">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="b4069-126">DistinguishedName</span></span>  

 <span data-ttu-id="b4069-127">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b4069-127">Data type: string</span></span>  
  
 <span data-ttu-id="b4069-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4069-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4069-129">Nombre de servicio en la dirección.</span><span class="sxs-lookup"><span data-stu-id="b4069-129">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="b4069-130">Extensiones</span><span class="sxs-lookup"><span data-stu-id="b4069-130">Extensions</span></span>  

 <span data-ttu-id="b4069-131">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="b4069-131">Data type: string array</span></span>  
  
 <span data-ttu-id="b4069-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4069-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4069-133">Los contextos de instancia para las extensiones de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="b4069-133">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="b4069-134">Metadatos</span><span class="sxs-lookup"><span data-stu-id="b4069-134">Metadata</span></span>  

 <span data-ttu-id="b4069-135">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="b4069-135">Data type: string array</span></span>  
  
 <span data-ttu-id="b4069-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4069-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4069-137">Los valores de metadatos de servicio.</span><span class="sxs-lookup"><span data-stu-id="b4069-137">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="b4069-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="b4069-138">Name</span></span>  

 <span data-ttu-id="b4069-139">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b4069-139">Data type: string</span></span>  
  
 <span data-ttu-id="b4069-140">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4069-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4069-141">El nombre único de este servicio.</span><span class="sxs-lookup"><span data-stu-id="b4069-141">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="b4069-142">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b4069-142">Namespace</span></span>  

 <span data-ttu-id="b4069-143">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b4069-143">Data type: string</span></span>  
  
 <span data-ttu-id="b4069-144">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4069-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4069-145">El espacio de nombres del servicio.</span><span class="sxs-lookup"><span data-stu-id="b4069-145">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="b4069-146">Abierto</span><span class="sxs-lookup"><span data-stu-id="b4069-146">Opened</span></span>  

 <span data-ttu-id="b4069-147">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="b4069-147">Data type: datetime</span></span>  
  
 <span data-ttu-id="b4069-148">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4069-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4069-149">El momento en el que se abrió el servicio.</span><span class="sxs-lookup"><span data-stu-id="b4069-149">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="b4069-150">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="b4069-150">OutgoingChannels</span></span>  

 <span data-ttu-id="b4069-151">Tipo de datos: matriz de canal</span><span class="sxs-lookup"><span data-stu-id="b4069-151">Data type: Channel array</span></span>  
  
 <span data-ttu-id="b4069-152">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4069-152">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4069-153">Los canales que salen de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="b4069-153">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="b4069-154">ProcessId</span><span class="sxs-lookup"><span data-stu-id="b4069-154">ProcessId</span></span>  

 <span data-ttu-id="b4069-155">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="b4069-155">Data type: sint32</span></span>  
  
 <span data-ttu-id="b4069-156">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4069-156">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4069-157">El id. de proceso que hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="b4069-157">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4069-158">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4069-158">Requirements</span></span>  
  
|<span data-ttu-id="b4069-159">MOF</span><span class="sxs-lookup"><span data-stu-id="b4069-159">MOF</span></span>|<span data-ttu-id="b4069-160">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b4069-160">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b4069-161">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b4069-161">Namespace</span></span>|<span data-ttu-id="b4069-162">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b4069-162">Defined in root\ServiceModel</span></span>|
