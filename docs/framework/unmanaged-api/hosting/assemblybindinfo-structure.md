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
ms.openlocfilehash: 615637813b08629aaea74b23fa2737f52d61bafb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616929"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="0bb62-102">AssemblyBindInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="0bb62-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="0bb62-103">Proporciona información detallada acerca del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="0bb62-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bb62-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0bb62-104">Syntax</span></span>  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="0bb62-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0bb62-105">Members</span></span>  
  
|<span data-ttu-id="0bb62-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="0bb62-106">Member</span></span>|<span data-ttu-id="0bb62-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bb62-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="0bb62-108">Un identificador único para el `IStream` devuelto por una llamada a [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md), desde el que se va a cargar el ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="0bb62-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="0bb62-109">Identificador único para el ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="0bb62-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="0bb62-110">Identificador del ensamblado al que se hace referencia después de la aplicación de los valores de directiva de enlace.</span><span class="sxs-lookup"><span data-stu-id="0bb62-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="0bb62-111">Uno de los valores de [EPolicyAction](epolicyaction-enumeration.md) que indican qué directivas de control de versiones, si las hay, deben aplicarse al ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="0bb62-111">One of the [EPolicyAction](epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bb62-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0bb62-112">Remarks</span></span>  
 <span data-ttu-id="0bb62-113">El host proporciona el identificador único `dwAppDomainId` al Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0bb62-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="0bb62-114">Después de una llamada a `IHostAssemblyStore::ProvideAssembly` , el tiempo de ejecución utiliza el identificador para determinar si `IStream` se ha asignado el contenido de.</span><span class="sxs-lookup"><span data-stu-id="0bb62-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="0bb62-115">En ese caso, el tiempo de ejecución carga la copia existente en lugar de reasignar la secuencia.</span><span class="sxs-lookup"><span data-stu-id="0bb62-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="0bb62-116">El Runtime también utiliza este identificador como clave de búsqueda para las secuencias devueltas por las llamadas a [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md).</span><span class="sxs-lookup"><span data-stu-id="0bb62-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="0bb62-117">Por lo tanto, el identificador debe ser único para las solicitudes de módulo y para las solicitudes de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0bb62-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bb62-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0bb62-118">Requirements</span></span>  
 <span data-ttu-id="0bb62-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bb62-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bb62-120">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="0bb62-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="0bb62-121">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0bb62-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0bb62-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bb62-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bb62-123">Consulta también</span><span class="sxs-lookup"><span data-stu-id="0bb62-123">See also</span></span>

- [<span data-ttu-id="0bb62-124">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="0bb62-124">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="0bb62-125">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bb62-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="0bb62-126">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bb62-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="0bb62-127">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bb62-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="0bb62-128">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bb62-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="0bb62-129">ModuleBindInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="0bb62-129">ModuleBindInfo Structure</span></span>](modulebindinfo-structure.md)
