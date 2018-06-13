---
title: web de Office
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: 0cfeb178e26f6c93e29210accf5d7866cc1fca02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487152"
---
# <a name="service"></a><span data-ttu-id="26db3-102">web de Office</span><span class="sxs-lookup"><span data-stu-id="26db3-102">Service</span></span>
<span data-ttu-id="26db3-103">web de Office</span><span class="sxs-lookup"><span data-stu-id="26db3-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26db3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26db3-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="26db3-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="26db3-105">Methods</span></span>  
 <span data-ttu-id="26db3-106">La clase Service no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="26db3-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="26db3-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="26db3-107">Properties</span></span>  
 <span data-ttu-id="26db3-108">La clase Service posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="26db3-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="26db3-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="26db3-109">BaseAddresses</span></span>  
 <span data-ttu-id="26db3-110">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="26db3-110">Data type: string array</span></span>  
  
 <span data-ttu-id="26db3-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26db3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26db3-112">Las direcciones base utilizadas por el servicio.</span><span class="sxs-lookup"><span data-stu-id="26db3-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="26db3-113">comportamientos</span><span class="sxs-lookup"><span data-stu-id="26db3-113">Behaviors</span></span>  
 <span data-ttu-id="26db3-114">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="26db3-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="26db3-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26db3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26db3-116">Los comportamientos asociados a este servicio.</span><span class="sxs-lookup"><span data-stu-id="26db3-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="26db3-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="26db3-117">ConfigurationName</span></span>  
 <span data-ttu-id="26db3-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="26db3-118">Data type: string</span></span>  
  
 <span data-ttu-id="26db3-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26db3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26db3-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="26db3-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="26db3-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="26db3-121">CounterInstanceName</span></span>  
 <span data-ttu-id="26db3-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="26db3-122">Data type: string</span></span>  
  
 <span data-ttu-id="26db3-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26db3-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26db3-124">Nombre de la instancia de los contadores de rendimiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="26db3-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="26db3-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="26db3-125">DistinguishedName</span></span>  
 <span data-ttu-id="26db3-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="26db3-126">Data type: string</span></span>  
  
 <span data-ttu-id="26db3-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26db3-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26db3-128">Nombre de servicio en la dirección.</span><span class="sxs-lookup"><span data-stu-id="26db3-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="26db3-129">Extensiones</span><span class="sxs-lookup"><span data-stu-id="26db3-129">Extensions</span></span>  
 <span data-ttu-id="26db3-130">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="26db3-130">Data type: string array</span></span>  
  
 <span data-ttu-id="26db3-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26db3-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26db3-132">Los contextos de instancia para las extensiones de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="26db3-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="26db3-133">Metadatos</span><span class="sxs-lookup"><span data-stu-id="26db3-133">Metadata</span></span>  
 <span data-ttu-id="26db3-134">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="26db3-134">Data type: string array</span></span>  
  
 <span data-ttu-id="26db3-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26db3-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26db3-136">Los valores de metadatos de servicio.</span><span class="sxs-lookup"><span data-stu-id="26db3-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="26db3-137">nombre</span><span class="sxs-lookup"><span data-stu-id="26db3-137">Name</span></span>  
 <span data-ttu-id="26db3-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="26db3-138">Data type: string</span></span>  
  
 <span data-ttu-id="26db3-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26db3-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26db3-140">El nombre único de este servicio.</span><span class="sxs-lookup"><span data-stu-id="26db3-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="26db3-141">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="26db3-141">Namespace</span></span>  
 <span data-ttu-id="26db3-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="26db3-142">Data type: string</span></span>  
  
 <span data-ttu-id="26db3-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26db3-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26db3-144">El espacio de nombres del servicio.</span><span class="sxs-lookup"><span data-stu-id="26db3-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="26db3-145">Abierto</span><span class="sxs-lookup"><span data-stu-id="26db3-145">Opened</span></span>  
 <span data-ttu-id="26db3-146">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="26db3-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="26db3-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26db3-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26db3-148">El momento en el que se abrió el servicio.</span><span class="sxs-lookup"><span data-stu-id="26db3-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="26db3-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="26db3-149">OutgoingChannels</span></span>  
 <span data-ttu-id="26db3-150">Tipo de datos: matriz de canal</span><span class="sxs-lookup"><span data-stu-id="26db3-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="26db3-151">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26db3-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26db3-152">Los canales que salen de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="26db3-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="26db3-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="26db3-153">ProcessId</span></span>  
 <span data-ttu-id="26db3-154">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="26db3-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="26db3-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26db3-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26db3-156">El id. de proceso que hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="26db3-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26db3-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26db3-157">Requirements</span></span>  
  
|<span data-ttu-id="26db3-158">MOF</span><span class="sxs-lookup"><span data-stu-id="26db3-158">MOF</span></span>|<span data-ttu-id="26db3-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="26db3-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="26db3-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="26db3-160">Namespace</span></span>|<span data-ttu-id="26db3-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="26db3-161">Defined in root\ServiceModel</span></span>|
