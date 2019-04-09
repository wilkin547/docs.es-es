---
title: ModuleBindInfo (Estructura)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f14d3dcaad1cc8cac11599b1647d61df3a793301
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124454"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="03910-102">ModuleBindInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="03910-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="03910-103">Proporciona información detallada sobre el módulo que se hace referencia y el ensamblado que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="03910-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03910-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03910-104">Syntax</span></span>  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="03910-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="03910-105">Members</span></span>  
  
|<span data-ttu-id="03910-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="03910-106">Member</span></span>|<span data-ttu-id="03910-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="03910-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="03910-108">Un identificador único para el `IStream` devuelto por una llamada a la [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) método desde el que se puede cargar el módulo que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="03910-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="03910-109">Un identificador único para el ensamblado que contiene el módulo que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="03910-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="03910-110">El nombre del módulo que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="03910-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03910-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03910-111">Remarks</span></span>  
 `ModuleBindInfo` <span data-ttu-id="03910-112">se pasa como parámetro a `IHostAssemblyStore::ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="03910-112">is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="03910-113">El host proporciona el identificador único `dwAppDomainId` a common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="03910-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="03910-114">Después de llamar a la [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) método finaliza, el tiempo de ejecución utiliza el identificador para determinar si el contenido de la `IStream` se han asignado.</span><span class="sxs-lookup"><span data-stu-id="03910-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="03910-115">Si es así, el tiempo de ejecución carga la copia existente en lugar de reasignar la secuencia.</span><span class="sxs-lookup"><span data-stu-id="03910-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="03910-116">El tiempo de ejecución también utiliza este identificador como una clave de búsqueda para las secuencias que se devuelven de las llamadas a la `IHostAssemblyStore::ProvideAssembly` método.</span><span class="sxs-lookup"><span data-stu-id="03910-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="03910-117">Por lo tanto, el identificador debe ser único para las solicitudes de módulos en cuanto a las solicitudes de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="03910-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03910-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03910-118">Requirements</span></span>  
 <span data-ttu-id="03910-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03910-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03910-120">**Encabezado**: MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="03910-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="03910-121">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="03910-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="03910-122">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="03910-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="03910-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="03910-123">See also</span></span>

- [<span data-ttu-id="03910-124">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="03910-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="03910-125">AssemblyBindInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="03910-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [<span data-ttu-id="03910-126">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="03910-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="03910-127">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="03910-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="03910-128">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="03910-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
