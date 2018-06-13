---
title: punto de conexión
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 5d597e9e029cec3552c94b47a64dfbf36d933e67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487651"
---
# <a name="endpoint"></a><span data-ttu-id="d2246-102">punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d2246-102">Endpoint</span></span>
<span data-ttu-id="d2246-103">punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d2246-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2246-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2246-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="d2246-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d2246-105">Methods</span></span>  
 <span data-ttu-id="d2246-106">La clase Endpoint define el método siguiente.</span><span class="sxs-lookup"><span data-stu-id="d2246-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="d2246-107">Método</span><span class="sxs-lookup"><span data-stu-id="d2246-107">Method</span></span>|<span data-ttu-id="d2246-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2246-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d2246-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="d2246-109">GetOperationCounterInstanceName</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|<span data-ttu-id="d2246-110">Recupera el nombre de instancia del contador de rendimiento de la operación</span><span class="sxs-lookup"><span data-stu-id="d2246-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="d2246-111">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d2246-111">Properties</span></span>  
 <span data-ttu-id="d2246-112">La clase Endpoint posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d2246-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="d2246-113">Dirección</span><span class="sxs-lookup"><span data-stu-id="d2246-113">Address</span></span>  
 <span data-ttu-id="d2246-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d2246-114">Data type: string</span></span>  
  
 <span data-ttu-id="d2246-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d2246-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d2246-116">Un URI que contiene la dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="d2246-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="d2246-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="d2246-117">AddressHeaders</span></span>  
 <span data-ttu-id="d2246-118">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="d2246-118">Data type: string array</span></span>  
  
 <span data-ttu-id="d2246-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d2246-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d2246-120">La colección de encabezados de dirección adjunta a este extremo.</span><span class="sxs-lookup"><span data-stu-id="d2246-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="d2246-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="d2246-121">AddressIdentity</span></span>  
 <span data-ttu-id="d2246-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d2246-122">Data type: string</span></span>  
  
 <span data-ttu-id="d2246-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d2246-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d2246-124">La identidad del extremo.</span><span class="sxs-lookup"><span data-stu-id="d2246-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="d2246-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="d2246-125">AppDomainId</span></span>  
 <span data-ttu-id="d2246-126">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="d2246-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="d2246-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d2246-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d2246-128">El id. del appdomain que hospeda al extremo.</span><span class="sxs-lookup"><span data-stu-id="d2246-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="d2246-129">Controles de comportamiento</span><span class="sxs-lookup"><span data-stu-id="d2246-129">Behaviors</span></span>  
 <span data-ttu-id="d2246-130">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="d2246-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="d2246-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d2246-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d2246-132">Colección de comportamientos implementada por este extremo.</span><span class="sxs-lookup"><span data-stu-id="d2246-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="d2246-133">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d2246-133">Binding</span></span>  
 <span data-ttu-id="d2246-134">Tipo de datos: enlace</span><span class="sxs-lookup"><span data-stu-id="d2246-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="d2246-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d2246-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d2246-136">El enlace utilizado por este extremo.</span><span class="sxs-lookup"><span data-stu-id="d2246-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="d2246-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="d2246-137">ContractName</span></span>  
 <span data-ttu-id="d2246-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d2246-138">Data type: string</span></span>  
  
 <span data-ttu-id="d2246-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d2246-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d2246-140">Cadena que especifica qué contrato está exponiendo este extremo.</span><span class="sxs-lookup"><span data-stu-id="d2246-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="d2246-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="d2246-141">CounterInstanceName</span></span>  
 <span data-ttu-id="d2246-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d2246-142">Data type: string</span></span>  
  
 <span data-ttu-id="d2246-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d2246-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d2246-144">Nombre de la instancia del contador de rendimiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="d2246-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="d2246-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="d2246-145">ListenUri</span></span>  
 <span data-ttu-id="d2246-146">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d2246-146">Data type: string</span></span>  
  
 <span data-ttu-id="d2246-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d2246-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d2246-148">El URI en el que el extremo realiza escuchas.</span><span class="sxs-lookup"><span data-stu-id="d2246-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="d2246-149">Name</span><span class="sxs-lookup"><span data-stu-id="d2246-149">Name</span></span>  
 <span data-ttu-id="d2246-150">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d2246-150">Data type: string</span></span>  
  
 <span data-ttu-id="d2246-151">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d2246-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d2246-152">El nombre único de este extremo.</span><span class="sxs-lookup"><span data-stu-id="d2246-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="d2246-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="d2246-153">ProcessId</span></span>  
 <span data-ttu-id="d2246-154">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="d2246-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="d2246-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d2246-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d2246-156">El Id. del proceso que hospeda al extremo.</span><span class="sxs-lookup"><span data-stu-id="d2246-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="d2246-157">ref</span><span class="sxs-lookup"><span data-stu-id="d2246-157">ref</span></span>  
 <span data-ttu-id="d2246-158">Tipo de datos: Contrato</span><span class="sxs-lookup"><span data-stu-id="d2246-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="d2246-159">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d2246-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d2246-160">El contrato que este extremo está exponiendo.</span><span class="sxs-lookup"><span data-stu-id="d2246-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2246-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2246-161">Requirements</span></span>  
  
|<span data-ttu-id="d2246-162">MOF</span><span class="sxs-lookup"><span data-stu-id="d2246-162">MOF</span></span>|<span data-ttu-id="d2246-163">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d2246-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d2246-164">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="d2246-164">Namespace</span></span>|<span data-ttu-id="d2246-165">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d2246-165">Defined in root\ServiceModel</span></span>|
