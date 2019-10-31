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
ms.openlocfilehash: ae40d8adaae70ccff6e8058858a506267d58873f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133746"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="4a1ec-102">ModuleBindInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="4a1ec-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="4a1ec-103">Proporciona información detallada sobre el módulo al que se hace referencia y el ensamblado que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="4a1ec-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a1ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a1ec-104">Syntax</span></span>  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="4a1ec-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4a1ec-105">Members</span></span>  
  
|<span data-ttu-id="4a1ec-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4a1ec-106">Member</span></span>|<span data-ttu-id="4a1ec-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a1ec-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="4a1ec-108">Un identificador único para el `IStream` devuelto por una llamada al método [IHostAssemblyStore::P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) desde el que se va a cargar el módulo al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="4a1ec-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="4a1ec-109">Un identificador único para el ensamblado que contiene el módulo al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="4a1ec-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="4a1ec-110">Nombre del módulo al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="4a1ec-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a1ec-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a1ec-111">Remarks</span></span>  
 <span data-ttu-id="4a1ec-112">`ModuleBindInfo` se pasa como parámetro a `IHostAssemblyStore::ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="4a1ec-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="4a1ec-113">El host proporciona el identificador único `dwAppDomainId` al Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4a1ec-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="4a1ec-114">Después de que se devuelva una llamada al método [IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) , el motor en tiempo de ejecución utiliza el identificador para determinar si se ha asignado el contenido de la `IStream`.</span><span class="sxs-lookup"><span data-stu-id="4a1ec-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="4a1ec-115">En ese caso, el tiempo de ejecución carga la copia existente en lugar de reasignar la secuencia.</span><span class="sxs-lookup"><span data-stu-id="4a1ec-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="4a1ec-116">El motor en tiempo de ejecución también utiliza este identificador como clave de búsqueda para las secuencias devueltas por las llamadas al método `IHostAssemblyStore::ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="4a1ec-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="4a1ec-117">Por lo tanto, el identificador debe ser único para las solicitudes de módulo y para las solicitudes de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4a1ec-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a1ec-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a1ec-118">Requirements</span></span>  
 <span data-ttu-id="4a1ec-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a1ec-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a1ec-120">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="4a1ec-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="4a1ec-121">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4a1ec-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a1ec-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a1ec-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a1ec-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a1ec-123">See also</span></span>

- [<span data-ttu-id="4a1ec-124">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="4a1ec-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="4a1ec-125">AssemblyBindInfo (estructura)</span><span class="sxs-lookup"><span data-stu-id="4a1ec-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [<span data-ttu-id="4a1ec-126">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a1ec-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="4a1ec-127">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a1ec-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="4a1ec-128">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a1ec-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
