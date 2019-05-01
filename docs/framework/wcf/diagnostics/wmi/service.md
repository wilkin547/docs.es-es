---
title: web de Office
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: c59672b3b7617d9c28d99f7d534b6e7f2f2e9fbb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991450"
---
# <a name="service"></a><span data-ttu-id="8d0bc-102">web de Office</span><span class="sxs-lookup"><span data-stu-id="8d0bc-102">Service</span></span>
<span data-ttu-id="8d0bc-103">web de Office</span><span class="sxs-lookup"><span data-stu-id="8d0bc-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d0bc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d0bc-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="8d0bc-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8d0bc-105">Methods</span></span>  
 <span data-ttu-id="8d0bc-106">La clase Service no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8d0bc-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8d0bc-107">Properties</span></span>  
 <span data-ttu-id="8d0bc-108">La clase Service posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="8d0bc-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="8d0bc-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="8d0bc-109">BaseAddresses</span></span>  
 <span data-ttu-id="8d0bc-110">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="8d0bc-110">Data type: string array</span></span>  
  
 <span data-ttu-id="8d0bc-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8d0bc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d0bc-112">Las direcciones base utilizadas por el servicio.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="8d0bc-113">comportamientos</span><span class="sxs-lookup"><span data-stu-id="8d0bc-113">Behaviors</span></span>  
 <span data-ttu-id="8d0bc-114">Tipo de datos: Matriz de comportamiento</span><span class="sxs-lookup"><span data-stu-id="8d0bc-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="8d0bc-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8d0bc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d0bc-116">Los comportamientos asociados a este servicio.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="8d0bc-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="8d0bc-117">ConfigurationName</span></span>  
 <span data-ttu-id="8d0bc-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8d0bc-118">Data type: string</span></span>  
  
 <span data-ttu-id="8d0bc-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8d0bc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d0bc-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d0bc-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="8d0bc-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="8d0bc-121">CounterInstanceName</span></span>  
 <span data-ttu-id="8d0bc-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8d0bc-122">Data type: string</span></span>  
  
 <span data-ttu-id="8d0bc-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8d0bc-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d0bc-124">Nombre de la instancia de los contadores de rendimiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="8d0bc-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="8d0bc-125">DistinguishedName</span></span>  
 <span data-ttu-id="8d0bc-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8d0bc-126">Data type: string</span></span>  
  
 <span data-ttu-id="8d0bc-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8d0bc-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d0bc-128">Nombre de servicio en la dirección.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="8d0bc-129">Extensiones</span><span class="sxs-lookup"><span data-stu-id="8d0bc-129">Extensions</span></span>  
 <span data-ttu-id="8d0bc-130">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="8d0bc-130">Data type: string array</span></span>  
  
 <span data-ttu-id="8d0bc-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8d0bc-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d0bc-132">Los contextos de instancia para las extensiones de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="8d0bc-133">Metadatos</span><span class="sxs-lookup"><span data-stu-id="8d0bc-133">Metadata</span></span>  
 <span data-ttu-id="8d0bc-134">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="8d0bc-134">Data type: string array</span></span>  
  
 <span data-ttu-id="8d0bc-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8d0bc-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d0bc-136">Los valores de metadatos de servicio.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="8d0bc-137">Name</span><span class="sxs-lookup"><span data-stu-id="8d0bc-137">Name</span></span>  
 <span data-ttu-id="8d0bc-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8d0bc-138">Data type: string</span></span>  
  
 <span data-ttu-id="8d0bc-139">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8d0bc-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d0bc-140">El nombre único de este servicio.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="8d0bc-141">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="8d0bc-141">Namespace</span></span>  
 <span data-ttu-id="8d0bc-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8d0bc-142">Data type: string</span></span>  
  
 <span data-ttu-id="8d0bc-143">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8d0bc-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d0bc-144">El espacio de nombres del servicio.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="8d0bc-145">Abierto</span><span class="sxs-lookup"><span data-stu-id="8d0bc-145">Opened</span></span>  
 <span data-ttu-id="8d0bc-146">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="8d0bc-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="8d0bc-147">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8d0bc-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d0bc-148">El momento en el que se abrió el servicio.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="8d0bc-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="8d0bc-149">OutgoingChannels</span></span>  
 <span data-ttu-id="8d0bc-150">Tipo de datos: Matriz de canal</span><span class="sxs-lookup"><span data-stu-id="8d0bc-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="8d0bc-151">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8d0bc-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d0bc-152">Los canales que salen de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="8d0bc-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="8d0bc-153">ProcessId</span></span>  
 <span data-ttu-id="8d0bc-154">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="8d0bc-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="8d0bc-155">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8d0bc-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d0bc-156">El id. de proceso que hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d0bc-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d0bc-157">Requirements</span></span>  
  
|<span data-ttu-id="8d0bc-158">MOF</span><span class="sxs-lookup"><span data-stu-id="8d0bc-158">MOF</span></span>|<span data-ttu-id="8d0bc-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8d0bc-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="8d0bc-160">Namespace</span></span>|<span data-ttu-id="8d0bc-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8d0bc-161">Defined in root\ServiceModel</span></span>|
