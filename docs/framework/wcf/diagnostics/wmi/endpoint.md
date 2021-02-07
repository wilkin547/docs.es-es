---
description: 'Más información acerca de: punto de conexión'
title: Punto de conexión
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 1c28be37d1b1abfe1813e6da8903809affd309e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757467"
---
# <a name="endpoint"></a><span data-ttu-id="bf98e-103">Punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bf98e-103">Endpoint</span></span>

<span data-ttu-id="bf98e-104">Punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bf98e-104">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf98e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf98e-105">Syntax</span></span>  
  
```csharp
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bf98e-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="bf98e-106">Methods</span></span>  

 <span data-ttu-id="bf98e-107">La clase Endpoint define el método siguiente.</span><span class="sxs-lookup"><span data-stu-id="bf98e-107">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="bf98e-108">Método</span><span class="sxs-lookup"><span data-stu-id="bf98e-108">Method</span></span>|<span data-ttu-id="bf98e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf98e-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf98e-110">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="bf98e-110">GetOperationCounterInstanceName</span></span>](getoperationcounterinstancename.md)|<span data-ttu-id="bf98e-111">Recupera el nombre de instancia del contador de rendimiento de la operación</span><span class="sxs-lookup"><span data-stu-id="bf98e-111">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="bf98e-112">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bf98e-112">Properties</span></span>  

 <span data-ttu-id="bf98e-113">La clase Endpoint posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="bf98e-113">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="bf98e-114">Dirección</span><span class="sxs-lookup"><span data-stu-id="bf98e-114">Address</span></span>  

 <span data-ttu-id="bf98e-115">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bf98e-115">Data type: string</span></span>  
  
 <span data-ttu-id="bf98e-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf98e-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf98e-117">Un URI que contiene la dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="bf98e-117">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="bf98e-118">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="bf98e-118">AddressHeaders</span></span>  

 <span data-ttu-id="bf98e-119">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="bf98e-119">Data type: string array</span></span>  
  
 <span data-ttu-id="bf98e-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf98e-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf98e-121">La colección de encabezados de dirección adjunta a este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bf98e-121">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="bf98e-122">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="bf98e-122">AddressIdentity</span></span>  

 <span data-ttu-id="bf98e-123">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bf98e-123">Data type: string</span></span>  
  
 <span data-ttu-id="bf98e-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf98e-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf98e-125">La identidad del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bf98e-125">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="bf98e-126">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="bf98e-126">AppDomainId</span></span>  

 <span data-ttu-id="bf98e-127">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="bf98e-127">Data type: sint32</span></span>  
  
 <span data-ttu-id="bf98e-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf98e-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf98e-129">El id. del appdomain que hospeda al punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bf98e-129">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="bf98e-130">Comportamientos</span><span class="sxs-lookup"><span data-stu-id="bf98e-130">Behaviors</span></span>  

 <span data-ttu-id="bf98e-131">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="bf98e-131">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="bf98e-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf98e-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf98e-133">Colección de comportamientos implementada por este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bf98e-133">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="bf98e-134">Enlace</span><span class="sxs-lookup"><span data-stu-id="bf98e-134">Binding</span></span>  

 <span data-ttu-id="bf98e-135">Tipo de datos: enlace</span><span class="sxs-lookup"><span data-stu-id="bf98e-135">Data type: Binding</span></span>  
  
 <span data-ttu-id="bf98e-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf98e-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf98e-137">El enlace utilizado por este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bf98e-137">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="bf98e-138">ContractName</span><span class="sxs-lookup"><span data-stu-id="bf98e-138">ContractName</span></span>  

 <span data-ttu-id="bf98e-139">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bf98e-139">Data type: string</span></span>  
  
 <span data-ttu-id="bf98e-140">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf98e-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf98e-141">Cadena que especifica qué contrato está exponiendo este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bf98e-141">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="bf98e-142">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="bf98e-142">CounterInstanceName</span></span>  

 <span data-ttu-id="bf98e-143">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bf98e-143">Data type: string</span></span>  
  
 <span data-ttu-id="bf98e-144">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf98e-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf98e-145">Nombre de la instancia del contador de rendimiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="bf98e-145">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="bf98e-146">ListenUri</span><span class="sxs-lookup"><span data-stu-id="bf98e-146">ListenUri</span></span>  

 <span data-ttu-id="bf98e-147">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bf98e-147">Data type: string</span></span>  
  
 <span data-ttu-id="bf98e-148">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf98e-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf98e-149">El URI en el que el extremo realiza escuchas.</span><span class="sxs-lookup"><span data-stu-id="bf98e-149">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="bf98e-150">Nombre</span><span class="sxs-lookup"><span data-stu-id="bf98e-150">Name</span></span>  

 <span data-ttu-id="bf98e-151">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bf98e-151">Data type: string</span></span>  
  
 <span data-ttu-id="bf98e-152">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf98e-152">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf98e-153">El nombre único de este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bf98e-153">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="bf98e-154">ProcessId</span><span class="sxs-lookup"><span data-stu-id="bf98e-154">ProcessId</span></span>  

 <span data-ttu-id="bf98e-155">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="bf98e-155">Data type: sint32</span></span>  
  
 <span data-ttu-id="bf98e-156">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf98e-156">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf98e-157">El Id. del proceso que hospeda al extremo.</span><span class="sxs-lookup"><span data-stu-id="bf98e-157">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="bf98e-158">ref</span><span class="sxs-lookup"><span data-stu-id="bf98e-158">ref</span></span>  

 <span data-ttu-id="bf98e-159">Tipo de datos: Contrato</span><span class="sxs-lookup"><span data-stu-id="bf98e-159">Data type: Contract</span></span>  
  
 <span data-ttu-id="bf98e-160">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf98e-160">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf98e-161">El contrato que este punto de conexión está exponiendo.</span><span class="sxs-lookup"><span data-stu-id="bf98e-161">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf98e-162">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf98e-162">Requirements</span></span>  
  
|<span data-ttu-id="bf98e-163">MOF</span><span class="sxs-lookup"><span data-stu-id="bf98e-163">MOF</span></span>|<span data-ttu-id="bf98e-164">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bf98e-164">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bf98e-165">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="bf98e-165">Namespace</span></span>|<span data-ttu-id="bf98e-166">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bf98e-166">Defined in root\ServiceModel</span></span>|
