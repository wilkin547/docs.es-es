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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b209e568b1e65ed785155d045cd48d1248672da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209806"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="6bb5a-102">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6bb5a-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="6bb5a-103">Proporciona métodos que admiten la comunicación entre el host y common language runtime (CLR) acerca de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="6bb5a-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6bb5a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6bb5a-104">Methods</span></span>  
  
|<span data-ttu-id="6bb5a-105">Método</span><span class="sxs-lookup"><span data-stu-id="6bb5a-105">Method</span></span>|<span data-ttu-id="6bb5a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6bb5a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6bb5a-107">GetBindingIdentityFromFile (método)</span><span class="sxs-lookup"><span data-stu-id="6bb5a-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="6bb5a-108">Obtiene la identidad del ensamblado enlace de datos para el ensamblado en la ruta de acceso de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="6bb5a-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="6bb5a-109">GetBindingIdentityFromStream (método)</span><span class="sxs-lookup"><span data-stu-id="6bb5a-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="6bb5a-110">Obtiene los datos de identidad de ensamblado canónico para el ensamblado en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="6bb5a-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="6bb5a-111">GetCLRAssemblyReferenceList (método)</span><span class="sxs-lookup"><span data-stu-id="6bb5a-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="6bb5a-112">Obtiene un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instancia desde la lista proporcionada de identidades de ensamblado parciales.</span><span class="sxs-lookup"><span data-stu-id="6bb5a-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="6bb5a-113">GetProbingAssembliesFromReference (método)</span><span class="sxs-lookup"><span data-stu-id="6bb5a-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="6bb5a-114">Obtiene un [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerador para las identidades de ensamblado al que hace referencia el ensamblado con la identidad especificada.</span><span class="sxs-lookup"><span data-stu-id="6bb5a-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="6bb5a-115">GetReferencedAssembliesFromFile (método)</span><span class="sxs-lookup"><span data-stu-id="6bb5a-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="6bb5a-116">Obtiene un [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instancia que contiene una lista de ensamblados al que hace referencia el ensamblado en la ruta de acceso de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="6bb5a-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="6bb5a-117">GetReferencedAssembliesFromStream (método)</span><span class="sxs-lookup"><span data-stu-id="6bb5a-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="6bb5a-118">Obtiene un puntero a un `ICLRReferenceAssemblyEnum` objeto que contiene datos de identidad de ensamblado para los ensamblados que se hace referencia el ensamblado en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="6bb5a-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="6bb5a-119">IsStronglyNamed (método)</span><span class="sxs-lookup"><span data-stu-id="6bb5a-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="6bb5a-120">Obtiene un valor que indica si el ensamblado especificado tiene un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="6bb5a-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bb5a-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6bb5a-121">Remarks</span></span>  
 <span data-ttu-id="6bb5a-122">Use `ICLRAssemblyIdentityManager` obtener instancias de `ICLRAssemblyReferenceList` y enumerar las identidades de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6bb5a-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bb5a-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6bb5a-123">Requirements</span></span>  
 <span data-ttu-id="6bb5a-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bb5a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bb5a-125">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6bb5a-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6bb5a-126">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6bb5a-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6bb5a-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bb5a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bb5a-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bb5a-128">See also</span></span>

- [<span data-ttu-id="6bb5a-129">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6bb5a-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="6bb5a-130">ICLRProbingAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6bb5a-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="6bb5a-131">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="6bb5a-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
