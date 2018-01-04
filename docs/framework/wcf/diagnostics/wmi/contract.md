---
title: Contract1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04a5cb87b9ed61fd278ce0f2e05e5f1c954de5b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="contract"></a><span data-ttu-id="b0326-102">Contrato</span><span class="sxs-lookup"><span data-stu-id="b0326-102">Contract</span></span>
<span data-ttu-id="b0326-103">Contrato</span><span class="sxs-lookup"><span data-stu-id="b0326-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0326-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0326-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="b0326-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b0326-105">Methods</span></span>  
 <span data-ttu-id="b0326-106">La clase Contrato no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="b0326-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b0326-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b0326-107">Properties</span></span>  
 <span data-ttu-id="b0326-108">La clase Contrato tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b0326-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="b0326-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="b0326-109">AppDomainId</span></span>  
 <span data-ttu-id="b0326-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="b0326-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="b0326-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b0326-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0326-112">El id. del appdomain de appdomain que hospeda el contrato.</span><span class="sxs-lookup"><span data-stu-id="b0326-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="b0326-113">Comportamientos</span><span class="sxs-lookup"><span data-stu-id="b0326-113">Behaviors</span></span>  
 <span data-ttu-id="b0326-114">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="b0326-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="b0326-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b0326-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0326-116">Los comportamientos asociados a este contrato.</span><span class="sxs-lookup"><span data-stu-id="b0326-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="b0326-117">nombre</span><span class="sxs-lookup"><span data-stu-id="b0326-117">Name</span></span>  
 <span data-ttu-id="b0326-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b0326-118">Data type: string</span></span>  
  
 <span data-ttu-id="b0326-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b0326-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0326-120">Nombre del contrato en WSDL.</span><span class="sxs-lookup"><span data-stu-id="b0326-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="b0326-121">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b0326-121">Namespace</span></span>  
 <span data-ttu-id="b0326-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b0326-122">Data type: string</span></span>  
  
 <span data-ttu-id="b0326-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b0326-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0326-124">El espacio de nombres del elemento `portType` en WSDL.</span><span class="sxs-lookup"><span data-stu-id="b0326-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="b0326-125">Operaciones</span><span class="sxs-lookup"><span data-stu-id="b0326-125">Operations</span></span>  
 <span data-ttu-id="b0326-126">Tipo de datos: matriz de operación</span><span class="sxs-lookup"><span data-stu-id="b0326-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="b0326-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b0326-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0326-128">Las operaciones de este contrato.</span><span class="sxs-lookup"><span data-stu-id="b0326-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="b0326-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="b0326-129">ProcessId</span></span>  
 <span data-ttu-id="b0326-130">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="b0326-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="b0326-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b0326-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0326-132">El Identificador del proceso del proceso que hospeda el contrato.</span><span class="sxs-lookup"><span data-stu-id="b0326-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="b0326-133">ref</span><span class="sxs-lookup"><span data-stu-id="b0326-133">ref</span></span>  
 <span data-ttu-id="b0326-134">Tipo de datos: Contrato</span><span class="sxs-lookup"><span data-stu-id="b0326-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="b0326-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b0326-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0326-136">El tipo de devolución de llamada cuando el contrato es un contrato dúplex.</span><span class="sxs-lookup"><span data-stu-id="b0326-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="b0326-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="b0326-137">SessionMode</span></span>  
 <span data-ttu-id="b0326-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b0326-138">Data type: string</span></span>  
  
 <span data-ttu-id="b0326-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b0326-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0326-140">Indica si el contrato requiere el enlace asociado a este contrato para utilizar las sesiones del canal.</span><span class="sxs-lookup"><span data-stu-id="b0326-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="b0326-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="b0326-141">Type</span></span>  
 <span data-ttu-id="b0326-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b0326-142">Data type: string</span></span>  
  
 <span data-ttu-id="b0326-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b0326-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0326-144">Tipo del contrato.</span><span class="sxs-lookup"><span data-stu-id="b0326-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0326-145">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0326-145">Requirements</span></span>  
  
|<span data-ttu-id="b0326-146">MOF</span><span class="sxs-lookup"><span data-stu-id="b0326-146">MOF</span></span>|<span data-ttu-id="b0326-147">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b0326-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b0326-148">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b0326-148">Namespace</span></span>|<span data-ttu-id="b0326-149">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b0326-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0326-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0326-150">See Also</span></span>  
 <xref:System.ServiceModel.Description.ContractDescription>
