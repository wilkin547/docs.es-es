---
title: Contrato
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 0df39bbd0b273f1e898ccbe585be288cc245b7f5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274145"
---
# <a name="contract"></a><span data-ttu-id="c99c5-102">Contrato</span><span class="sxs-lookup"><span data-stu-id="c99c5-102">Contract</span></span>

<span data-ttu-id="c99c5-103">Contrato</span><span class="sxs-lookup"><span data-stu-id="c99c5-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c99c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c99c5-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="c99c5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c99c5-105">Methods</span></span>  

 <span data-ttu-id="c99c5-106">La clase Contrato no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="c99c5-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c99c5-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c99c5-107">Properties</span></span>  

 <span data-ttu-id="c99c5-108">La clase Contrato tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="c99c5-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="c99c5-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="c99c5-109">AppDomainId</span></span>  

 <span data-ttu-id="c99c5-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="c99c5-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="c99c5-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c99c5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c99c5-112">El id. del appdomain de appdomain que hospeda el contrato.</span><span class="sxs-lookup"><span data-stu-id="c99c5-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="c99c5-113">Comportamientos</span><span class="sxs-lookup"><span data-stu-id="c99c5-113">Behaviors</span></span>  

 <span data-ttu-id="c99c5-114">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="c99c5-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="c99c5-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c99c5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c99c5-116">Los comportamientos asociados a este contrato.</span><span class="sxs-lookup"><span data-stu-id="c99c5-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="c99c5-117">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="c99c5-117">Name</span></span>  

 <span data-ttu-id="c99c5-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c99c5-118">Data type: string</span></span>  
  
 <span data-ttu-id="c99c5-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c99c5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c99c5-120">Nombre del contrato en WSDL.</span><span class="sxs-lookup"><span data-stu-id="c99c5-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="c99c5-121">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="c99c5-121">Namespace</span></span>  

 <span data-ttu-id="c99c5-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c99c5-122">Data type: string</span></span>  
  
 <span data-ttu-id="c99c5-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c99c5-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c99c5-124">El espacio de nombres del elemento `portType` en WSDL.</span><span class="sxs-lookup"><span data-stu-id="c99c5-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="c99c5-125">Operations</span><span class="sxs-lookup"><span data-stu-id="c99c5-125">Operations</span></span>  

 <span data-ttu-id="c99c5-126">Tipo de datos: matriz de operación</span><span class="sxs-lookup"><span data-stu-id="c99c5-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="c99c5-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c99c5-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c99c5-128">Las operaciones de este contrato.</span><span class="sxs-lookup"><span data-stu-id="c99c5-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="c99c5-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="c99c5-129">ProcessId</span></span>  

 <span data-ttu-id="c99c5-130">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="c99c5-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="c99c5-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c99c5-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c99c5-132">El Identificador del proceso del proceso que hospeda el contrato.</span><span class="sxs-lookup"><span data-stu-id="c99c5-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="c99c5-133">ref</span><span class="sxs-lookup"><span data-stu-id="c99c5-133">ref</span></span>  

 <span data-ttu-id="c99c5-134">Tipo de datos: Contrato</span><span class="sxs-lookup"><span data-stu-id="c99c5-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="c99c5-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c99c5-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c99c5-136">El tipo de devolución de llamada cuando el contrato es un contrato dúplex.</span><span class="sxs-lookup"><span data-stu-id="c99c5-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="c99c5-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="c99c5-137">SessionMode</span></span>  

 <span data-ttu-id="c99c5-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c99c5-138">Data type: string</span></span>  
  
 <span data-ttu-id="c99c5-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c99c5-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c99c5-140">Indica si el contrato requiere el enlace asociado a este contrato para utilizar las sesiones del canal.</span><span class="sxs-lookup"><span data-stu-id="c99c5-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="c99c5-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="c99c5-141">Type</span></span>  

 <span data-ttu-id="c99c5-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c99c5-142">Data type: string</span></span>  
  
 <span data-ttu-id="c99c5-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c99c5-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c99c5-144">Tipo del contrato.</span><span class="sxs-lookup"><span data-stu-id="c99c5-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c99c5-145">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c99c5-145">Requirements</span></span>  
  
|<span data-ttu-id="c99c5-146">MOF</span><span class="sxs-lookup"><span data-stu-id="c99c5-146">MOF</span></span>|<span data-ttu-id="c99c5-147">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c99c5-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c99c5-148">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="c99c5-148">Namespace</span></span>|<span data-ttu-id="c99c5-149">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c99c5-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c99c5-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="c99c5-150">See also</span></span>

- <xref:System.ServiceModel.Description.ContractDescription>
