---
title: punto de conexión
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 4562481e8b0b18c0ea0d9df0af3427ffe6419821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963610"
---
# <a name="endpoint"></a><span data-ttu-id="b2bc3-102">punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b2bc3-102">Endpoint</span></span>
<span data-ttu-id="b2bc3-103">punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b2bc3-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2bc3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2bc3-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="b2bc3-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b2bc3-105">Methods</span></span>  
 <span data-ttu-id="b2bc3-106">La clase Endpoint define el método siguiente.</span><span class="sxs-lookup"><span data-stu-id="b2bc3-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="b2bc3-107">Método</span><span class="sxs-lookup"><span data-stu-id="b2bc3-107">Method</span></span>|<span data-ttu-id="b2bc3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2bc3-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2bc3-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="b2bc3-109">GetOperationCounterInstanceName</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|<span data-ttu-id="b2bc3-110">Recupera el nombre de instancia del contador de rendimiento de la operación</span><span class="sxs-lookup"><span data-stu-id="b2bc3-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="b2bc3-111">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b2bc3-111">Properties</span></span>  
 <span data-ttu-id="b2bc3-112">La clase Endpoint posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b2bc3-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="b2bc3-113">Dirección</span><span class="sxs-lookup"><span data-stu-id="b2bc3-113">Address</span></span>  
 <span data-ttu-id="b2bc3-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b2bc3-114">Data type: string</span></span>  
  
 <span data-ttu-id="b2bc3-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="b2bc3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b2bc3-116">Un URI que contiene la dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="b2bc3-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="b2bc3-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="b2bc3-117">AddressHeaders</span></span>  
 <span data-ttu-id="b2bc3-118">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="b2bc3-118">Data type: string array</span></span>  
  
 <span data-ttu-id="b2bc3-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="b2bc3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b2bc3-120">La colección de encabezados de dirección adjunta a este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b2bc3-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="b2bc3-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="b2bc3-121">AddressIdentity</span></span>  
 <span data-ttu-id="b2bc3-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b2bc3-122">Data type: string</span></span>  
  
 <span data-ttu-id="b2bc3-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="b2bc3-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b2bc3-124">La identidad del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b2bc3-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="b2bc3-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="b2bc3-125">AppDomainId</span></span>  
 <span data-ttu-id="b2bc3-126">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="b2bc3-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="b2bc3-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="b2bc3-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b2bc3-128">El id. del appdomain que hospeda al punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b2bc3-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="b2bc3-129">comportamientos</span><span class="sxs-lookup"><span data-stu-id="b2bc3-129">Behaviors</span></span>  
 <span data-ttu-id="b2bc3-130">Tipo de datos: Matriz de comportamiento</span><span class="sxs-lookup"><span data-stu-id="b2bc3-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="b2bc3-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="b2bc3-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b2bc3-132">Colección de comportamientos implementada por este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b2bc3-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="b2bc3-133">Enlaces</span><span class="sxs-lookup"><span data-stu-id="b2bc3-133">Binding</span></span>  
 <span data-ttu-id="b2bc3-134">Tipo de datos: Enlaces</span><span class="sxs-lookup"><span data-stu-id="b2bc3-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="b2bc3-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="b2bc3-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b2bc3-136">El enlace utilizado por este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b2bc3-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="b2bc3-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="b2bc3-137">ContractName</span></span>  
 <span data-ttu-id="b2bc3-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b2bc3-138">Data type: string</span></span>  
  
 <span data-ttu-id="b2bc3-139">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="b2bc3-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b2bc3-140">Cadena que especifica qué contrato está exponiendo este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b2bc3-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="b2bc3-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="b2bc3-141">CounterInstanceName</span></span>  
 <span data-ttu-id="b2bc3-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b2bc3-142">Data type: string</span></span>  
  
 <span data-ttu-id="b2bc3-143">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="b2bc3-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b2bc3-144">Nombre de la instancia del contador de rendimiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="b2bc3-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="b2bc3-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="b2bc3-145">ListenUri</span></span>  
 <span data-ttu-id="b2bc3-146">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b2bc3-146">Data type: string</span></span>  
  
 <span data-ttu-id="b2bc3-147">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="b2bc3-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b2bc3-148">El URI en el que el extremo realiza escuchas.</span><span class="sxs-lookup"><span data-stu-id="b2bc3-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="b2bc3-149">Name</span><span class="sxs-lookup"><span data-stu-id="b2bc3-149">Name</span></span>  
 <span data-ttu-id="b2bc3-150">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b2bc3-150">Data type: string</span></span>  
  
 <span data-ttu-id="b2bc3-151">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="b2bc3-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b2bc3-152">El nombre único de este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b2bc3-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="b2bc3-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="b2bc3-153">ProcessId</span></span>  
 <span data-ttu-id="b2bc3-154">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="b2bc3-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="b2bc3-155">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="b2bc3-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b2bc3-156">El Id. del proceso que hospeda al extremo.</span><span class="sxs-lookup"><span data-stu-id="b2bc3-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="b2bc3-157">ref</span><span class="sxs-lookup"><span data-stu-id="b2bc3-157">ref</span></span>  
 <span data-ttu-id="b2bc3-158">Tipo de datos: Contrato</span><span class="sxs-lookup"><span data-stu-id="b2bc3-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="b2bc3-159">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="b2bc3-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b2bc3-160">El contrato que este punto de conexión está exponiendo.</span><span class="sxs-lookup"><span data-stu-id="b2bc3-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2bc3-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2bc3-161">Requirements</span></span>  
  
|<span data-ttu-id="b2bc3-162">MOF</span><span class="sxs-lookup"><span data-stu-id="b2bc3-162">MOF</span></span>|<span data-ttu-id="b2bc3-163">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b2bc3-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b2bc3-164">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b2bc3-164">Namespace</span></span>|<span data-ttu-id="b2bc3-165">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b2bc3-165">Defined in root\ServiceModel</span></span>|
