---
title: AssemblyBindInfo (Estructura)
ms.date: 03/30/2017
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce79987c7fcf45b8d10dcc4613e053ee735941de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112819"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="8f153-102">AssemblyBindInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="8f153-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="8f153-103">Proporciona información detallada sobre el ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="8f153-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f153-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f153-104">Syntax</span></span>  
  
```  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="8f153-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8f153-105">Members</span></span>  
  
|<span data-ttu-id="8f153-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="8f153-106">Member</span></span>|<span data-ttu-id="8f153-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f153-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="8f153-108">Un identificador único para el `IStream` devuelto por una llamada a [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), desde la que tiene que se puede cargar el ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="8f153-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="8f153-109">Un identificador único para el ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="8f153-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="8f153-110">El identificador para el ensamblado que se hace referencia después de la aplicación de los valores de directiva de enlace.</span><span class="sxs-lookup"><span data-stu-id="8f153-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="8f153-111">Uno de los [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores que indican qué directivas de control de versiones, si los hay, deben aplicarse al ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="8f153-111">One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f153-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8f153-112">Remarks</span></span>  
 <span data-ttu-id="8f153-113">El host proporciona el identificador único `dwAppDomainId` a common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8f153-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="8f153-114">Después de llamar a `IHostAssemblyStore::ProvideAssembly` devuelve, el tiempo de ejecución utiliza el identificador para determinar si el contenido de la `IStream` se han asignado.</span><span class="sxs-lookup"><span data-stu-id="8f153-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="8f153-115">Si es así, el tiempo de ejecución carga la copia existente en lugar de reasignar la secuencia.</span><span class="sxs-lookup"><span data-stu-id="8f153-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="8f153-116">El tiempo de ejecución también utiliza este identificador como una clave de búsqueda para las secuencias devuelven por las llamadas a [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span><span class="sxs-lookup"><span data-stu-id="8f153-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="8f153-117">Por lo tanto, el identificador debe ser único para las solicitudes de módulo y para las solicitudes de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8f153-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f153-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f153-118">Requirements</span></span>  
 <span data-ttu-id="8f153-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f153-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f153-120">**Encabezado**: MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="8f153-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="8f153-121">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8f153-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f153-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f153-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f153-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f153-123">See also</span></span>

- [<span data-ttu-id="8f153-124">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8f153-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="8f153-125">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f153-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="8f153-126">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f153-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="8f153-127">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f153-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="8f153-128">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f153-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="8f153-129">ModuleBindInfo (estructura)</span><span class="sxs-lookup"><span data-stu-id="8f153-129">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
