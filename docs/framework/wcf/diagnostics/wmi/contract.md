---
description: 'Más información acerca de: contrato'
title: Contrato
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 3443a7d2eed1a34f07495bd3ceb98c1ba997fabf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757558"
---
# <a name="contract"></a><span data-ttu-id="4105e-103">Contrato</span><span class="sxs-lookup"><span data-stu-id="4105e-103">Contract</span></span>

<span data-ttu-id="4105e-104">Contrato</span><span class="sxs-lookup"><span data-stu-id="4105e-104">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4105e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4105e-105">Syntax</span></span>  
  
```csharp
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4105e-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="4105e-106">Methods</span></span>  

 <span data-ttu-id="4105e-107">La clase Contrato no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="4105e-107">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4105e-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4105e-108">Properties</span></span>  

 <span data-ttu-id="4105e-109">La clase Contrato tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="4105e-109">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="4105e-110">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="4105e-110">AppDomainId</span></span>  

 <span data-ttu-id="4105e-111">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="4105e-111">Data type: sint32</span></span>  
  
 <span data-ttu-id="4105e-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4105e-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4105e-113">El id. del appdomain de appdomain que hospeda el contrato.</span><span class="sxs-lookup"><span data-stu-id="4105e-113">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="4105e-114">Comportamientos</span><span class="sxs-lookup"><span data-stu-id="4105e-114">Behaviors</span></span>  

 <span data-ttu-id="4105e-115">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="4105e-115">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="4105e-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4105e-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4105e-117">Los comportamientos asociados a este contrato.</span><span class="sxs-lookup"><span data-stu-id="4105e-117">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="4105e-118">Nombre</span><span class="sxs-lookup"><span data-stu-id="4105e-118">Name</span></span>  

 <span data-ttu-id="4105e-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4105e-119">Data type: string</span></span>  
  
 <span data-ttu-id="4105e-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4105e-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4105e-121">Nombre del contrato en WSDL.</span><span class="sxs-lookup"><span data-stu-id="4105e-121">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="4105e-122">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="4105e-122">Namespace</span></span>  

 <span data-ttu-id="4105e-123">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4105e-123">Data type: string</span></span>  
  
 <span data-ttu-id="4105e-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4105e-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4105e-125">El espacio de nombres del elemento `portType` en WSDL.</span><span class="sxs-lookup"><span data-stu-id="4105e-125">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="4105e-126">Operaciones</span><span class="sxs-lookup"><span data-stu-id="4105e-126">Operations</span></span>  

 <span data-ttu-id="4105e-127">Tipo de datos: matriz de operación</span><span class="sxs-lookup"><span data-stu-id="4105e-127">Data type: Operation array</span></span>  
  
 <span data-ttu-id="4105e-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4105e-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4105e-129">Las operaciones de este contrato.</span><span class="sxs-lookup"><span data-stu-id="4105e-129">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="4105e-130">ProcessId</span><span class="sxs-lookup"><span data-stu-id="4105e-130">ProcessId</span></span>  

 <span data-ttu-id="4105e-131">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="4105e-131">Data type: sint32</span></span>  
  
 <span data-ttu-id="4105e-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4105e-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4105e-133">El Identificador del proceso del proceso que hospeda el contrato.</span><span class="sxs-lookup"><span data-stu-id="4105e-133">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="4105e-134">ref</span><span class="sxs-lookup"><span data-stu-id="4105e-134">ref</span></span>  

 <span data-ttu-id="4105e-135">Tipo de datos: Contrato</span><span class="sxs-lookup"><span data-stu-id="4105e-135">Data type: Contract</span></span>  
  
 <span data-ttu-id="4105e-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4105e-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4105e-137">El tipo de devolución de llamada cuando el contrato es un contrato dúplex.</span><span class="sxs-lookup"><span data-stu-id="4105e-137">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="4105e-138">SessionMode</span><span class="sxs-lookup"><span data-stu-id="4105e-138">SessionMode</span></span>  

 <span data-ttu-id="4105e-139">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4105e-139">Data type: string</span></span>  
  
 <span data-ttu-id="4105e-140">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4105e-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4105e-141">Indica si el contrato requiere el enlace asociado a este contrato para utilizar las sesiones del canal.</span><span class="sxs-lookup"><span data-stu-id="4105e-141">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="4105e-142">Tipo</span><span class="sxs-lookup"><span data-stu-id="4105e-142">Type</span></span>  

 <span data-ttu-id="4105e-143">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4105e-143">Data type: string</span></span>  
  
 <span data-ttu-id="4105e-144">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4105e-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4105e-145">Tipo del contrato.</span><span class="sxs-lookup"><span data-stu-id="4105e-145">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4105e-146">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4105e-146">Requirements</span></span>  
  
|<span data-ttu-id="4105e-147">MOF</span><span class="sxs-lookup"><span data-stu-id="4105e-147">MOF</span></span>|<span data-ttu-id="4105e-148">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4105e-148">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4105e-149">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="4105e-149">Namespace</span></span>|<span data-ttu-id="4105e-150">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4105e-150">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4105e-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="4105e-151">See also</span></span>

- <xref:System.ServiceModel.Description.ContractDescription>
