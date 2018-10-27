---
title: web de Office
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: c59672b3b7617d9c28d99f7d534b6e7f2f2e9fbb
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2018
ms.locfileid: "49633955"
---
# <a name="service"></a><span data-ttu-id="80231-102">web de Office</span><span class="sxs-lookup"><span data-stu-id="80231-102">Service</span></span>
<span data-ttu-id="80231-103">web de Office</span><span class="sxs-lookup"><span data-stu-id="80231-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80231-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80231-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="80231-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="80231-105">Methods</span></span>  
 <span data-ttu-id="80231-106">La clase Service no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="80231-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="80231-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="80231-107">Properties</span></span>  
 <span data-ttu-id="80231-108">La clase Service posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="80231-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="80231-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="80231-109">BaseAddresses</span></span>  
 <span data-ttu-id="80231-110">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="80231-110">Data type: string array</span></span>  
  
 <span data-ttu-id="80231-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="80231-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="80231-112">Las direcciones base utilizadas por el servicio.</span><span class="sxs-lookup"><span data-stu-id="80231-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="80231-113">comportamientos</span><span class="sxs-lookup"><span data-stu-id="80231-113">Behaviors</span></span>  
 <span data-ttu-id="80231-114">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="80231-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="80231-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="80231-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="80231-116">Los comportamientos asociados a este servicio.</span><span class="sxs-lookup"><span data-stu-id="80231-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="80231-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="80231-117">ConfigurationName</span></span>  
 <span data-ttu-id="80231-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="80231-118">Data type: string</span></span>  
  
 <span data-ttu-id="80231-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="80231-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="80231-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="80231-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="80231-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="80231-121">CounterInstanceName</span></span>  
 <span data-ttu-id="80231-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="80231-122">Data type: string</span></span>  
  
 <span data-ttu-id="80231-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="80231-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="80231-124">Nombre de la instancia de los contadores de rendimiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="80231-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="80231-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="80231-125">DistinguishedName</span></span>  
 <span data-ttu-id="80231-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="80231-126">Data type: string</span></span>  
  
 <span data-ttu-id="80231-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="80231-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="80231-128">Nombre de servicio en la dirección.</span><span class="sxs-lookup"><span data-stu-id="80231-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="80231-129">Extensiones</span><span class="sxs-lookup"><span data-stu-id="80231-129">Extensions</span></span>  
 <span data-ttu-id="80231-130">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="80231-130">Data type: string array</span></span>  
  
 <span data-ttu-id="80231-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="80231-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="80231-132">Los contextos de instancia para las extensiones de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="80231-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="80231-133">Metadatos</span><span class="sxs-lookup"><span data-stu-id="80231-133">Metadata</span></span>  
 <span data-ttu-id="80231-134">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="80231-134">Data type: string array</span></span>  
  
 <span data-ttu-id="80231-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="80231-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="80231-136">Los valores de metadatos de servicio.</span><span class="sxs-lookup"><span data-stu-id="80231-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="80231-137">nombre</span><span class="sxs-lookup"><span data-stu-id="80231-137">Name</span></span>  
 <span data-ttu-id="80231-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="80231-138">Data type: string</span></span>  
  
 <span data-ttu-id="80231-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="80231-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="80231-140">El nombre único de este servicio.</span><span class="sxs-lookup"><span data-stu-id="80231-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="80231-141">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="80231-141">Namespace</span></span>  
 <span data-ttu-id="80231-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="80231-142">Data type: string</span></span>  
  
 <span data-ttu-id="80231-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="80231-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="80231-144">El espacio de nombres del servicio.</span><span class="sxs-lookup"><span data-stu-id="80231-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="80231-145">Abierto</span><span class="sxs-lookup"><span data-stu-id="80231-145">Opened</span></span>  
 <span data-ttu-id="80231-146">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="80231-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="80231-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="80231-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="80231-148">El momento en el que se abrió el servicio.</span><span class="sxs-lookup"><span data-stu-id="80231-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="80231-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="80231-149">OutgoingChannels</span></span>  
 <span data-ttu-id="80231-150">Tipo de datos: matriz de canal</span><span class="sxs-lookup"><span data-stu-id="80231-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="80231-151">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="80231-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="80231-152">Los canales que salen de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="80231-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="80231-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="80231-153">ProcessId</span></span>  
 <span data-ttu-id="80231-154">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="80231-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="80231-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="80231-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="80231-156">El id. de proceso que hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="80231-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80231-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80231-157">Requirements</span></span>  
  
|<span data-ttu-id="80231-158">MOF</span><span class="sxs-lookup"><span data-stu-id="80231-158">MOF</span></span>|<span data-ttu-id="80231-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="80231-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="80231-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="80231-160">Namespace</span></span>|<span data-ttu-id="80231-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="80231-161">Defined in root\ServiceModel</span></span>|
