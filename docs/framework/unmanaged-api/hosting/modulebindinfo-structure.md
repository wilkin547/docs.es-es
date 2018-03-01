---
title: ModuleBindInfo (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 399ba2471b4dc7c5e372a56a9dcab8117068a693
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="722a0-102">ModuleBindInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="722a0-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="722a0-103">Proporciona información detallada sobre el módulo que se hace referencia y el ensamblado que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="722a0-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="722a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="722a0-104">Syntax</span></span>  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="722a0-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="722a0-105">Members</span></span>  
  
|<span data-ttu-id="722a0-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="722a0-106">Member</span></span>|<span data-ttu-id="722a0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="722a0-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="722a0-108">Un identificador único para la `IStream` devuelto por una llamada a la [IHostAssemblyStore:: ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) método desde el que se puede cargar el módulo que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="722a0-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="722a0-109">Un identificador único para el ensamblado que contiene el módulo que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="722a0-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="722a0-110">El nombre del módulo que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="722a0-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="722a0-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="722a0-111">Remarks</span></span>  
 <span data-ttu-id="722a0-112">`ModuleBindInfo`se pasa como un parámetro para `IHostAssemblyStore::ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="722a0-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="722a0-113">El host proporciona el identificador único `dwAppDomainId` a common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="722a0-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="722a0-114">Después de llamar a la [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) método vuelve, el tiempo de ejecución utiliza el identificador para determinar si el contenido de la `IStream` se han asignado.</span><span class="sxs-lookup"><span data-stu-id="722a0-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="722a0-115">Si es así, el tiempo de ejecución carga la copia existente en lugar de volver a asignar la secuencia.</span><span class="sxs-lookup"><span data-stu-id="722a0-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="722a0-116">El tiempo de ejecución también utiliza este identificador como una clave de búsqueda para las secuencias que se devuelven de las llamadas a la `IHostAssemblyStore::ProvideAssembly` método.</span><span class="sxs-lookup"><span data-stu-id="722a0-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="722a0-117">Por lo tanto, el identificador debe ser único para las solicitudes de módulo, así como para las solicitudes de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="722a0-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="722a0-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="722a0-118">Requirements</span></span>  
 <span data-ttu-id="722a0-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="722a0-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="722a0-120">**Encabezado:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="722a0-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="722a0-121">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="722a0-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="722a0-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="722a0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="722a0-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="722a0-123">See Also</span></span>  
 [<span data-ttu-id="722a0-124">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="722a0-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="722a0-125">AssemblyBindInfo (estructura)</span><span class="sxs-lookup"><span data-stu-id="722a0-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 [<span data-ttu-id="722a0-126">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="722a0-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="722a0-127">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="722a0-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="722a0-128">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="722a0-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
