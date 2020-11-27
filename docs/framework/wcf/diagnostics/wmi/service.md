---
title: Servicio
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: aa4eecbcc8a2ef818cd99d777b0e3c2f1f222e46
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273287"
---
# <a name="service"></a><span data-ttu-id="6dd16-102">Servicio</span><span class="sxs-lookup"><span data-stu-id="6dd16-102">Service</span></span>

<span data-ttu-id="6dd16-103">Servicio</span><span class="sxs-lookup"><span data-stu-id="6dd16-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dd16-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6dd16-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="6dd16-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6dd16-105">Methods</span></span>  

 <span data-ttu-id="6dd16-106">La clase Service no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="6dd16-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6dd16-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6dd16-107">Properties</span></span>  

 <span data-ttu-id="6dd16-108">La clase Service posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="6dd16-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="6dd16-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="6dd16-109">BaseAddresses</span></span>  

 <span data-ttu-id="6dd16-110">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="6dd16-110">Data type: string array</span></span>  
  
 <span data-ttu-id="6dd16-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6dd16-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6dd16-112">Las direcciones base utilizadas por el servicio.</span><span class="sxs-lookup"><span data-stu-id="6dd16-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="6dd16-113">Comportamientos</span><span class="sxs-lookup"><span data-stu-id="6dd16-113">Behaviors</span></span>  

 <span data-ttu-id="6dd16-114">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="6dd16-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="6dd16-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6dd16-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6dd16-116">Los comportamientos asociados a este servicio.</span><span class="sxs-lookup"><span data-stu-id="6dd16-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="6dd16-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="6dd16-117">ConfigurationName</span></span>  

 <span data-ttu-id="6dd16-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6dd16-118">Data type: string</span></span>  
  
 <span data-ttu-id="6dd16-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6dd16-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6dd16-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="6dd16-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="6dd16-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="6dd16-121">CounterInstanceName</span></span>  

 <span data-ttu-id="6dd16-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6dd16-122">Data type: string</span></span>  
  
 <span data-ttu-id="6dd16-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6dd16-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6dd16-124">Nombre de la instancia de los contadores de rendimiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="6dd16-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="6dd16-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="6dd16-125">DistinguishedName</span></span>  

 <span data-ttu-id="6dd16-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6dd16-126">Data type: string</span></span>  
  
 <span data-ttu-id="6dd16-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6dd16-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6dd16-128">Nombre de servicio en la dirección.</span><span class="sxs-lookup"><span data-stu-id="6dd16-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="6dd16-129">Extensiones</span><span class="sxs-lookup"><span data-stu-id="6dd16-129">Extensions</span></span>  

 <span data-ttu-id="6dd16-130">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="6dd16-130">Data type: string array</span></span>  
  
 <span data-ttu-id="6dd16-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6dd16-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6dd16-132">Los contextos de instancia para las extensiones de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="6dd16-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="6dd16-133">Metadatos</span><span class="sxs-lookup"><span data-stu-id="6dd16-133">Metadata</span></span>  

 <span data-ttu-id="6dd16-134">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="6dd16-134">Data type: string array</span></span>  
  
 <span data-ttu-id="6dd16-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6dd16-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6dd16-136">Los valores de metadatos de servicio.</span><span class="sxs-lookup"><span data-stu-id="6dd16-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="6dd16-137">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6dd16-137">Name</span></span>  

 <span data-ttu-id="6dd16-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6dd16-138">Data type: string</span></span>  
  
 <span data-ttu-id="6dd16-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6dd16-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6dd16-140">El nombre único de este servicio.</span><span class="sxs-lookup"><span data-stu-id="6dd16-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="6dd16-141">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6dd16-141">Namespace</span></span>  

 <span data-ttu-id="6dd16-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6dd16-142">Data type: string</span></span>  
  
 <span data-ttu-id="6dd16-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6dd16-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6dd16-144">El espacio de nombres del servicio.</span><span class="sxs-lookup"><span data-stu-id="6dd16-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="6dd16-145">Abierto</span><span class="sxs-lookup"><span data-stu-id="6dd16-145">Opened</span></span>  

 <span data-ttu-id="6dd16-146">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="6dd16-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="6dd16-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6dd16-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6dd16-148">El momento en el que se abrió el servicio.</span><span class="sxs-lookup"><span data-stu-id="6dd16-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="6dd16-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="6dd16-149">OutgoingChannels</span></span>  

 <span data-ttu-id="6dd16-150">Tipo de datos: matriz de canal</span><span class="sxs-lookup"><span data-stu-id="6dd16-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="6dd16-151">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6dd16-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6dd16-152">Los canales que salen de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="6dd16-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="6dd16-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="6dd16-153">ProcessId</span></span>  

 <span data-ttu-id="6dd16-154">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="6dd16-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="6dd16-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6dd16-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6dd16-156">El id. de proceso que hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="6dd16-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dd16-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6dd16-157">Requirements</span></span>  
  
|<span data-ttu-id="6dd16-158">MOF</span><span class="sxs-lookup"><span data-stu-id="6dd16-158">MOF</span></span>|<span data-ttu-id="6dd16-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6dd16-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6dd16-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6dd16-160">Namespace</span></span>|<span data-ttu-id="6dd16-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6dd16-161">Defined in root\ServiceModel</span></span>|
