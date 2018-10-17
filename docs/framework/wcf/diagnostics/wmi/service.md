---
title: web de Office
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: c59672b3b7617d9c28d99f7d534b6e7f2f2e9fbb
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374220"
---
# <a name="service"></a><span data-ttu-id="acca7-102">web de Office</span><span class="sxs-lookup"><span data-stu-id="acca7-102">Service</span></span>
<span data-ttu-id="acca7-103">web de Office</span><span class="sxs-lookup"><span data-stu-id="acca7-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acca7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acca7-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="acca7-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="acca7-105">Methods</span></span>  
 <span data-ttu-id="acca7-106">La clase Service no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="acca7-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="acca7-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="acca7-107">Properties</span></span>  
 <span data-ttu-id="acca7-108">La clase Service posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="acca7-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="acca7-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="acca7-109">BaseAddresses</span></span>  
 <span data-ttu-id="acca7-110">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="acca7-110">Data type: string array</span></span>  
  
 <span data-ttu-id="acca7-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="acca7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="acca7-112">Las direcciones base utilizadas por el servicio.</span><span class="sxs-lookup"><span data-stu-id="acca7-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="acca7-113">comportamientos</span><span class="sxs-lookup"><span data-stu-id="acca7-113">Behaviors</span></span>  
 <span data-ttu-id="acca7-114">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="acca7-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="acca7-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="acca7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="acca7-116">Los comportamientos asociados a este servicio.</span><span class="sxs-lookup"><span data-stu-id="acca7-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="acca7-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="acca7-117">ConfigurationName</span></span>  
 <span data-ttu-id="acca7-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="acca7-118">Data type: string</span></span>  
  
 <span data-ttu-id="acca7-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="acca7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="acca7-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="acca7-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="acca7-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="acca7-121">CounterInstanceName</span></span>  
 <span data-ttu-id="acca7-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="acca7-122">Data type: string</span></span>  
  
 <span data-ttu-id="acca7-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="acca7-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="acca7-124">Nombre de la instancia de los contadores de rendimiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="acca7-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="acca7-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="acca7-125">DistinguishedName</span></span>  
 <span data-ttu-id="acca7-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="acca7-126">Data type: string</span></span>  
  
 <span data-ttu-id="acca7-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="acca7-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="acca7-128">Nombre de servicio en la dirección.</span><span class="sxs-lookup"><span data-stu-id="acca7-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="acca7-129">Extensiones</span><span class="sxs-lookup"><span data-stu-id="acca7-129">Extensions</span></span>  
 <span data-ttu-id="acca7-130">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="acca7-130">Data type: string array</span></span>  
  
 <span data-ttu-id="acca7-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="acca7-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="acca7-132">Los contextos de instancia para las extensiones de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="acca7-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="acca7-133">Metadatos</span><span class="sxs-lookup"><span data-stu-id="acca7-133">Metadata</span></span>  
 <span data-ttu-id="acca7-134">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="acca7-134">Data type: string array</span></span>  
  
 <span data-ttu-id="acca7-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="acca7-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="acca7-136">Los valores de metadatos de servicio.</span><span class="sxs-lookup"><span data-stu-id="acca7-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="acca7-137">nombre</span><span class="sxs-lookup"><span data-stu-id="acca7-137">Name</span></span>  
 <span data-ttu-id="acca7-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="acca7-138">Data type: string</span></span>  
  
 <span data-ttu-id="acca7-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="acca7-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="acca7-140">El nombre único de este servicio.</span><span class="sxs-lookup"><span data-stu-id="acca7-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="acca7-141">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="acca7-141">Namespace</span></span>  
 <span data-ttu-id="acca7-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="acca7-142">Data type: string</span></span>  
  
 <span data-ttu-id="acca7-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="acca7-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="acca7-144">El espacio de nombres del servicio.</span><span class="sxs-lookup"><span data-stu-id="acca7-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="acca7-145">Abierto</span><span class="sxs-lookup"><span data-stu-id="acca7-145">Opened</span></span>  
 <span data-ttu-id="acca7-146">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="acca7-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="acca7-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="acca7-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="acca7-148">El momento en el que se abrió el servicio.</span><span class="sxs-lookup"><span data-stu-id="acca7-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="acca7-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="acca7-149">OutgoingChannels</span></span>  
 <span data-ttu-id="acca7-150">Tipo de datos: matriz de canal</span><span class="sxs-lookup"><span data-stu-id="acca7-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="acca7-151">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="acca7-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="acca7-152">Los canales que salen de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="acca7-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="acca7-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="acca7-153">ProcessId</span></span>  
 <span data-ttu-id="acca7-154">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="acca7-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="acca7-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="acca7-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="acca7-156">El id. de proceso que hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="acca7-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acca7-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="acca7-157">Requirements</span></span>  
  
|<span data-ttu-id="acca7-158">MOF</span><span class="sxs-lookup"><span data-stu-id="acca7-158">MOF</span></span>|<span data-ttu-id="acca7-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="acca7-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="acca7-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="acca7-160">Namespace</span></span>|<span data-ttu-id="acca7-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="acca7-161">Defined in root\ServiceModel</span></span>|
