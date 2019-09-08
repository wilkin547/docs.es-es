---
title: Punto de conexión
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 03c401358839671d750985b95b1aada599931aad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795899"
---
# <a name="endpoint"></a><span data-ttu-id="3afc7-102">Punto de conexión</span><span class="sxs-lookup"><span data-stu-id="3afc7-102">Endpoint</span></span>
<span data-ttu-id="3afc7-103">Punto de conexión</span><span class="sxs-lookup"><span data-stu-id="3afc7-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3afc7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3afc7-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="3afc7-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3afc7-105">Methods</span></span>  
 <span data-ttu-id="3afc7-106">La clase Endpoint define el método siguiente.</span><span class="sxs-lookup"><span data-stu-id="3afc7-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="3afc7-107">Método</span><span class="sxs-lookup"><span data-stu-id="3afc7-107">Method</span></span>|<span data-ttu-id="3afc7-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3afc7-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3afc7-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="3afc7-109">GetOperationCounterInstanceName</span></span>](getoperationcounterinstancename.md)|<span data-ttu-id="3afc7-110">Recupera el nombre de instancia del contador de rendimiento de la operación</span><span class="sxs-lookup"><span data-stu-id="3afc7-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="3afc7-111">Properties (Propiedades)</span><span class="sxs-lookup"><span data-stu-id="3afc7-111">Properties</span></span>  
 <span data-ttu-id="3afc7-112">La clase Endpoint posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="3afc7-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="3afc7-113">Dirección</span><span class="sxs-lookup"><span data-stu-id="3afc7-113">Address</span></span>  
 <span data-ttu-id="3afc7-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="3afc7-114">Data type: string</span></span>  
  
 <span data-ttu-id="3afc7-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="3afc7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3afc7-116">Un URI que contiene la dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="3afc7-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="3afc7-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="3afc7-117">AddressHeaders</span></span>  
 <span data-ttu-id="3afc7-118">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="3afc7-118">Data type: string array</span></span>  
  
 <span data-ttu-id="3afc7-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="3afc7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3afc7-120">La colección de encabezados de dirección adjunta a este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3afc7-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="3afc7-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="3afc7-121">AddressIdentity</span></span>  
 <span data-ttu-id="3afc7-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="3afc7-122">Data type: string</span></span>  
  
 <span data-ttu-id="3afc7-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="3afc7-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3afc7-124">La identidad del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3afc7-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="3afc7-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="3afc7-125">AppDomainId</span></span>  
 <span data-ttu-id="3afc7-126">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="3afc7-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="3afc7-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="3afc7-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3afc7-128">El id. del appdomain que hospeda al punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3afc7-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="3afc7-129">comportamientos</span><span class="sxs-lookup"><span data-stu-id="3afc7-129">Behaviors</span></span>  
 <span data-ttu-id="3afc7-130">Tipo de datos: Matriz de comportamiento</span><span class="sxs-lookup"><span data-stu-id="3afc7-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="3afc7-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="3afc7-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3afc7-132">Colección de comportamientos implementada por este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3afc7-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="3afc7-133">Enlace</span><span class="sxs-lookup"><span data-stu-id="3afc7-133">Binding</span></span>  
 <span data-ttu-id="3afc7-134">Tipo de datos: Enlace</span><span class="sxs-lookup"><span data-stu-id="3afc7-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="3afc7-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="3afc7-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3afc7-136">El enlace utilizado por este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3afc7-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="3afc7-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="3afc7-137">ContractName</span></span>  
 <span data-ttu-id="3afc7-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="3afc7-138">Data type: string</span></span>  
  
 <span data-ttu-id="3afc7-139">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="3afc7-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3afc7-140">Cadena que especifica qué contrato está exponiendo este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3afc7-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="3afc7-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="3afc7-141">CounterInstanceName</span></span>  
 <span data-ttu-id="3afc7-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="3afc7-142">Data type: string</span></span>  
  
 <span data-ttu-id="3afc7-143">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="3afc7-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3afc7-144">Nombre de la instancia del contador de rendimiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="3afc7-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="3afc7-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="3afc7-145">ListenUri</span></span>  
 <span data-ttu-id="3afc7-146">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="3afc7-146">Data type: string</span></span>  
  
 <span data-ttu-id="3afc7-147">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="3afc7-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3afc7-148">El URI en el que el extremo realiza escuchas.</span><span class="sxs-lookup"><span data-stu-id="3afc7-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="3afc7-149">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="3afc7-149">Name</span></span>  
 <span data-ttu-id="3afc7-150">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="3afc7-150">Data type: string</span></span>  
  
 <span data-ttu-id="3afc7-151">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="3afc7-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3afc7-152">El nombre único de este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3afc7-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="3afc7-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="3afc7-153">ProcessId</span></span>  
 <span data-ttu-id="3afc7-154">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="3afc7-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="3afc7-155">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="3afc7-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3afc7-156">El Id. del proceso que hospeda al extremo.</span><span class="sxs-lookup"><span data-stu-id="3afc7-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="3afc7-157">ref</span><span class="sxs-lookup"><span data-stu-id="3afc7-157">ref</span></span>  
 <span data-ttu-id="3afc7-158">Tipo de datos: Contrato</span><span class="sxs-lookup"><span data-stu-id="3afc7-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="3afc7-159">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="3afc7-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3afc7-160">El contrato que este punto de conexión está exponiendo.</span><span class="sxs-lookup"><span data-stu-id="3afc7-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3afc7-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3afc7-161">Requirements</span></span>  
  
|<span data-ttu-id="3afc7-162">MOF</span><span class="sxs-lookup"><span data-stu-id="3afc7-162">MOF</span></span>|<span data-ttu-id="3afc7-163">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3afc7-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3afc7-164">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="3afc7-164">Namespace</span></span>|<span data-ttu-id="3afc7-165">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3afc7-165">Defined in root\ServiceModel</span></span>|
