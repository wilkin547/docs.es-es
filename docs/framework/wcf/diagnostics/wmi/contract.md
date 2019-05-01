---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 10789f9a2940c239ae20c8fd1e9d48bca0e820ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963701"
---
# <a name="contract"></a><span data-ttu-id="a991d-102">Contrato</span><span class="sxs-lookup"><span data-stu-id="a991d-102">Contract</span></span>
<span data-ttu-id="a991d-103">Contrato</span><span class="sxs-lookup"><span data-stu-id="a991d-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a991d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a991d-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="a991d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a991d-105">Methods</span></span>  
 <span data-ttu-id="a991d-106">La clase Contrato no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="a991d-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a991d-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a991d-107">Properties</span></span>  
 <span data-ttu-id="a991d-108">La clase Contrato tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="a991d-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="a991d-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="a991d-109">AppDomainId</span></span>  
 <span data-ttu-id="a991d-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="a991d-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="a991d-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="a991d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a991d-112">El id. del appdomain de appdomain que hospeda el contrato.</span><span class="sxs-lookup"><span data-stu-id="a991d-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="a991d-113">comportamientos</span><span class="sxs-lookup"><span data-stu-id="a991d-113">Behaviors</span></span>  
 <span data-ttu-id="a991d-114">Tipo de datos: Matriz de comportamiento</span><span class="sxs-lookup"><span data-stu-id="a991d-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="a991d-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="a991d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a991d-116">Los comportamientos asociados a este contrato.</span><span class="sxs-lookup"><span data-stu-id="a991d-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="a991d-117">Name</span><span class="sxs-lookup"><span data-stu-id="a991d-117">Name</span></span>  
 <span data-ttu-id="a991d-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="a991d-118">Data type: string</span></span>  
  
 <span data-ttu-id="a991d-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="a991d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a991d-120">Nombre del contrato en WSDL.</span><span class="sxs-lookup"><span data-stu-id="a991d-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="a991d-121">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a991d-121">Namespace</span></span>  
 <span data-ttu-id="a991d-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="a991d-122">Data type: string</span></span>  
  
 <span data-ttu-id="a991d-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="a991d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a991d-124">El espacio de nombres del elemento `portType` en WSDL.</span><span class="sxs-lookup"><span data-stu-id="a991d-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="a991d-125">Operaciones</span><span class="sxs-lookup"><span data-stu-id="a991d-125">Operations</span></span>  
 <span data-ttu-id="a991d-126">Tipo de datos: Matriz de operación</span><span class="sxs-lookup"><span data-stu-id="a991d-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="a991d-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="a991d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a991d-128">Las operaciones de este contrato.</span><span class="sxs-lookup"><span data-stu-id="a991d-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="a991d-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="a991d-129">ProcessId</span></span>  
 <span data-ttu-id="a991d-130">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="a991d-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="a991d-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="a991d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a991d-132">El Identificador del proceso del proceso que hospeda el contrato.</span><span class="sxs-lookup"><span data-stu-id="a991d-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="a991d-133">ref</span><span class="sxs-lookup"><span data-stu-id="a991d-133">ref</span></span>  
 <span data-ttu-id="a991d-134">Tipo de datos: Contrato</span><span class="sxs-lookup"><span data-stu-id="a991d-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="a991d-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="a991d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a991d-136">El tipo de devolución de llamada cuando el contrato es un contrato dúplex.</span><span class="sxs-lookup"><span data-stu-id="a991d-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="a991d-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="a991d-137">SessionMode</span></span>  
 <span data-ttu-id="a991d-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="a991d-138">Data type: string</span></span>  
  
 <span data-ttu-id="a991d-139">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="a991d-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a991d-140">Indica si el contrato requiere el enlace asociado a este contrato para utilizar las sesiones del canal.</span><span class="sxs-lookup"><span data-stu-id="a991d-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="a991d-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="a991d-141">Type</span></span>  
 <span data-ttu-id="a991d-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="a991d-142">Data type: string</span></span>  
  
 <span data-ttu-id="a991d-143">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="a991d-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a991d-144">Tipo del contrato.</span><span class="sxs-lookup"><span data-stu-id="a991d-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a991d-145">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a991d-145">Requirements</span></span>  
  
|<span data-ttu-id="a991d-146">MOF</span><span class="sxs-lookup"><span data-stu-id="a991d-146">MOF</span></span>|<span data-ttu-id="a991d-147">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a991d-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a991d-148">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a991d-148">Namespace</span></span>|<span data-ttu-id="a991d-149">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a991d-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a991d-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="a991d-150">See also</span></span>

- <xref:System.ServiceModel.Description.ContractDescription>
