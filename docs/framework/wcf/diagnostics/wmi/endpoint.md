---
title: "punto de conexión"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ed3c01f6943ec2958da56777ac0d6223fff66ab0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint"></a><span data-ttu-id="c3758-102">punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c3758-102">Endpoint</span></span>
<span data-ttu-id="c3758-103">punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c3758-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3758-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3758-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="c3758-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c3758-105">Methods</span></span>  
 <span data-ttu-id="c3758-106">La clase Endpoint define el método siguiente.</span><span class="sxs-lookup"><span data-stu-id="c3758-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="c3758-107">Método</span><span class="sxs-lookup"><span data-stu-id="c3758-107">Method</span></span>|<span data-ttu-id="c3758-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3758-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c3758-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="c3758-109">GetOperationCounterInstanceName</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|<span data-ttu-id="c3758-110">Recupera el nombre de instancia del contador de rendimiento de la operación</span><span class="sxs-lookup"><span data-stu-id="c3758-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="c3758-111">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c3758-111">Properties</span></span>  
 <span data-ttu-id="c3758-112">La clase Endpoint posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="c3758-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="c3758-113">Dirección</span><span class="sxs-lookup"><span data-stu-id="c3758-113">Address</span></span>  
 <span data-ttu-id="c3758-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c3758-114">Data type: string</span></span>  
  
 <span data-ttu-id="c3758-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c3758-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c3758-116">Un URI que contiene la dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="c3758-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="c3758-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="c3758-117">AddressHeaders</span></span>  
 <span data-ttu-id="c3758-118">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="c3758-118">Data type: string array</span></span>  
  
 <span data-ttu-id="c3758-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c3758-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c3758-120">La colección de encabezados de dirección adjunta a este extremo.</span><span class="sxs-lookup"><span data-stu-id="c3758-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="c3758-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="c3758-121">AddressIdentity</span></span>  
 <span data-ttu-id="c3758-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c3758-122">Data type: string</span></span>  
  
 <span data-ttu-id="c3758-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c3758-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c3758-124">La identidad del extremo.</span><span class="sxs-lookup"><span data-stu-id="c3758-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="c3758-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="c3758-125">AppDomainId</span></span>  
 <span data-ttu-id="c3758-126">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="c3758-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="c3758-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c3758-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c3758-128">El id. del appdomain que hospeda al extremo.</span><span class="sxs-lookup"><span data-stu-id="c3758-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="c3758-129">Controles de comportamiento</span><span class="sxs-lookup"><span data-stu-id="c3758-129">Behaviors</span></span>  
 <span data-ttu-id="c3758-130">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="c3758-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="c3758-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c3758-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c3758-132">Colección de comportamientos implementada por este extremo.</span><span class="sxs-lookup"><span data-stu-id="c3758-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="c3758-133">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c3758-133">Binding</span></span>  
 <span data-ttu-id="c3758-134">Tipo de datos: enlace</span><span class="sxs-lookup"><span data-stu-id="c3758-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="c3758-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c3758-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c3758-136">El enlace utilizado por este extremo.</span><span class="sxs-lookup"><span data-stu-id="c3758-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="c3758-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="c3758-137">ContractName</span></span>  
 <span data-ttu-id="c3758-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c3758-138">Data type: string</span></span>  
  
 <span data-ttu-id="c3758-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c3758-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c3758-140">Cadena que especifica qué contrato está exponiendo este extremo.</span><span class="sxs-lookup"><span data-stu-id="c3758-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="c3758-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="c3758-141">CounterInstanceName</span></span>  
 <span data-ttu-id="c3758-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c3758-142">Data type: string</span></span>  
  
 <span data-ttu-id="c3758-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c3758-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c3758-144">Nombre de la instancia del contador de rendimiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="c3758-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="c3758-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="c3758-145">ListenUri</span></span>  
 <span data-ttu-id="c3758-146">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c3758-146">Data type: string</span></span>  
  
 <span data-ttu-id="c3758-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c3758-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c3758-148">El URI en el que el extremo realiza escuchas.</span><span class="sxs-lookup"><span data-stu-id="c3758-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="c3758-149">Name</span><span class="sxs-lookup"><span data-stu-id="c3758-149">Name</span></span>  
 <span data-ttu-id="c3758-150">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c3758-150">Data type: string</span></span>  
  
 <span data-ttu-id="c3758-151">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c3758-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c3758-152">El nombre único de este extremo.</span><span class="sxs-lookup"><span data-stu-id="c3758-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="c3758-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="c3758-153">ProcessId</span></span>  
 <span data-ttu-id="c3758-154">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="c3758-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="c3758-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c3758-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c3758-156">El Id. del proceso que hospeda al extremo.</span><span class="sxs-lookup"><span data-stu-id="c3758-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="c3758-157">ref</span><span class="sxs-lookup"><span data-stu-id="c3758-157">ref</span></span>  
 <span data-ttu-id="c3758-158">Tipo de datos: Contrato</span><span class="sxs-lookup"><span data-stu-id="c3758-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="c3758-159">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c3758-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c3758-160">El contrato que este extremo está exponiendo.</span><span class="sxs-lookup"><span data-stu-id="c3758-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3758-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3758-161">Requirements</span></span>  
  
|<span data-ttu-id="c3758-162">MOF</span><span class="sxs-lookup"><span data-stu-id="c3758-162">MOF</span></span>|<span data-ttu-id="c3758-163">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c3758-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c3758-164">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="c3758-164">Namespace</span></span>|<span data-ttu-id="c3758-165">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c3758-165">Defined in root\ServiceModel</span></span>|
