---
description: 'Más información acerca de: interfaz ICLRAssemblyIdentityManager'
title: ICLRAssemblyIdentityManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
ms.openlocfilehash: d6238ec51a8cc1bb61eaa96e5297656c447df785
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790064"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="0293d-103">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0293d-103">ICLRAssemblyIdentityManager Interface</span></span>

<span data-ttu-id="0293d-104">Proporciona métodos que admiten la comunicación entre el host y el Common Language Runtime (CLR) acerca de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0293d-104">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0293d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="0293d-105">Methods</span></span>  
  
|<span data-ttu-id="0293d-106">Método</span><span class="sxs-lookup"><span data-stu-id="0293d-106">Method</span></span>|<span data-ttu-id="0293d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0293d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0293d-108">Método GetBindingIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="0293d-108">GetBindingIdentityFromFile Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="0293d-109">Obtiene los datos de enlace de identidad del ensamblado en la ruta de acceso de archivo especificada.</span><span class="sxs-lookup"><span data-stu-id="0293d-109">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="0293d-110">Método GetBindingIdentityFromStream</span><span class="sxs-lookup"><span data-stu-id="0293d-110">GetBindingIdentityFromStream Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="0293d-111">Obtiene los datos de identidad del ensamblado canónico para el ensamblado en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="0293d-111">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="0293d-112">Método GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="0293d-112">GetCLRAssemblyReferenceList Method</span></span>](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="0293d-113">Obtiene una instancia de [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) de la lista proporcionada de identidades de ensamblado parciales.</span><span class="sxs-lookup"><span data-stu-id="0293d-113">Gets an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="0293d-114">Método GetProbingAssembliesFromReference</span><span class="sxs-lookup"><span data-stu-id="0293d-114">GetProbingAssembliesFromReference Method</span></span>](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="0293d-115">Obtiene un enumerador [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) para las identidades de ensamblado a las que hace referencia el ensamblado con la identidad especificada.</span><span class="sxs-lookup"><span data-stu-id="0293d-115">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="0293d-116">Método GetReferencedAssembliesFromFile</span><span class="sxs-lookup"><span data-stu-id="0293d-116">GetReferencedAssembliesFromFile Method</span></span>](iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="0293d-117">Obtiene una instancia de [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) que contiene una lista de ensamblados a los que hace referencia el ensamblado en la ruta de acceso de archivo especificada.</span><span class="sxs-lookup"><span data-stu-id="0293d-117">Gets an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="0293d-118">Método GetReferencedAssembliesFromStream</span><span class="sxs-lookup"><span data-stu-id="0293d-118">GetReferencedAssembliesFromStream Method</span></span>](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="0293d-119">Obtiene un puntero a un `ICLRReferenceAssemblyEnum` objeto que contiene datos de identidad de ensamblado para los ensamblados a los que hace referencia el ensamblado en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="0293d-119">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="0293d-120">Método IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="0293d-120">IsStronglyNamed Method</span></span>](iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="0293d-121">Obtiene un valor que indica si el ensamblado especificado tiene un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="0293d-121">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0293d-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0293d-122">Remarks</span></span>  

 <span data-ttu-id="0293d-123">Utilice `ICLRAssemblyIdentityManager` para obtener instancias de `ICLRAssemblyReferenceList` y para enumerar las identidades de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0293d-123">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0293d-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0293d-124">Requirements</span></span>  

 <span data-ttu-id="0293d-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0293d-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0293d-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0293d-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0293d-127">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0293d-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0293d-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0293d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0293d-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="0293d-129">See also</span></span>

- [<span data-ttu-id="0293d-130">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0293d-130">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="0293d-131">ICLRProbingAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0293d-131">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="0293d-132">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="0293d-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
