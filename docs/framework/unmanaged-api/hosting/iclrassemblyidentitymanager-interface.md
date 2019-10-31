---
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
ms.openlocfilehash: 26de2ebf1364981d8b8f1fb38c8fa1045191114f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126626"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="13c42-102">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="13c42-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="13c42-103">Proporciona métodos que admiten la comunicación entre el host y el Common Language Runtime (CLR) acerca de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="13c42-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13c42-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="13c42-104">Methods</span></span>  
  
|<span data-ttu-id="13c42-105">Método</span><span class="sxs-lookup"><span data-stu-id="13c42-105">Method</span></span>|<span data-ttu-id="13c42-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="13c42-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13c42-107">GetBindingIdentityFromFile (método)</span><span class="sxs-lookup"><span data-stu-id="13c42-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="13c42-108">Obtiene los datos de enlace de identidad del ensamblado en la ruta de acceso de archivo especificada.</span><span class="sxs-lookup"><span data-stu-id="13c42-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="13c42-109">GetBindingIdentityFromStream (método)</span><span class="sxs-lookup"><span data-stu-id="13c42-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="13c42-110">Obtiene los datos de identidad del ensamblado canónico para el ensamblado en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="13c42-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="13c42-111">GetCLRAssemblyReferenceList (método)</span><span class="sxs-lookup"><span data-stu-id="13c42-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="13c42-112">Obtiene una instancia de [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) de la lista proporcionada de identidades de ensamblado parciales.</span><span class="sxs-lookup"><span data-stu-id="13c42-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="13c42-113">GetProbingAssembliesFromReference (método)</span><span class="sxs-lookup"><span data-stu-id="13c42-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="13c42-114">Obtiene un enumerador [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) para las identidades de ensamblado a las que hace referencia el ensamblado con la identidad especificada.</span><span class="sxs-lookup"><span data-stu-id="13c42-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="13c42-115">GetReferencedAssembliesFromFile (método)</span><span class="sxs-lookup"><span data-stu-id="13c42-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="13c42-116">Obtiene una instancia de [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) que contiene una lista de ensamblados a los que hace referencia el ensamblado en la ruta de acceso de archivo especificada.</span><span class="sxs-lookup"><span data-stu-id="13c42-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="13c42-117">GetReferencedAssembliesFromStream (método)</span><span class="sxs-lookup"><span data-stu-id="13c42-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="13c42-118">Obtiene un puntero a un `ICLRReferenceAssemblyEnum` objeto que contiene los datos de identidad del ensamblado para los ensamblados a los que hace referencia el ensamblado en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="13c42-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="13c42-119">IsStronglyNamed (método)</span><span class="sxs-lookup"><span data-stu-id="13c42-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="13c42-120">Obtiene un valor que indica si el ensamblado especificado tiene un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="13c42-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13c42-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13c42-121">Remarks</span></span>  
 <span data-ttu-id="13c42-122">Utilice `ICLRAssemblyIdentityManager` para obtener instancias de `ICLRAssemblyReferenceList` y para enumerar las identidades de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="13c42-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13c42-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13c42-123">Requirements</span></span>  
 <span data-ttu-id="13c42-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13c42-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13c42-125">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="13c42-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13c42-126">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="13c42-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13c42-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13c42-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13c42-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="13c42-128">See also</span></span>

- [<span data-ttu-id="13c42-129">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="13c42-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="13c42-130">ICLRProbingAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="13c42-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="13c42-131">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="13c42-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
