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
ms.openlocfilehash: 31be0525c637e50c1161129277d651b56dadfaa3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006771"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="8d99d-102">ModuleBindInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="8d99d-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="8d99d-103">Proporciona información detallada sobre el módulo al que se hace referencia y el ensamblado que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="8d99d-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d99d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d99d-104">Syntax</span></span>  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="8d99d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8d99d-105">Members</span></span>  
  
|<span data-ttu-id="8d99d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="8d99d-106">Member</span></span>|<span data-ttu-id="8d99d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d99d-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="8d99d-108">Un identificador único para el `IStream` devuelto por una llamada al método [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md) desde el que se va a cargar el módulo al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="8d99d-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="8d99d-109">Un identificador único para el ensamblado que contiene el módulo al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="8d99d-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="8d99d-110">Nombre del módulo al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="8d99d-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d99d-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8d99d-111">Remarks</span></span>  
 <span data-ttu-id="8d99d-112">`ModuleBindInfo`se pasa como un parámetro a `IHostAssemblyStore::ProvideModule` .</span><span class="sxs-lookup"><span data-stu-id="8d99d-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="8d99d-113">El host proporciona el identificador único `dwAppDomainId` al Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8d99d-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="8d99d-114">Después de que se devuelva una llamada al método [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) , el motor en tiempo de ejecución utiliza el identificador para determinar si `IStream` se ha asignado el contenido de.</span><span class="sxs-lookup"><span data-stu-id="8d99d-114">After a call to the [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="8d99d-115">En ese caso, el tiempo de ejecución carga la copia existente en lugar de reasignar la secuencia.</span><span class="sxs-lookup"><span data-stu-id="8d99d-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="8d99d-116">El Runtime también utiliza este identificador como clave de búsqueda para las secuencias que se devuelven desde las llamadas al `IHostAssemblyStore::ProvideAssembly` método.</span><span class="sxs-lookup"><span data-stu-id="8d99d-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="8d99d-117">Por lo tanto, el identificador debe ser único para las solicitudes de módulo y para las solicitudes de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8d99d-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d99d-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d99d-118">Requirements</span></span>  
 <span data-ttu-id="8d99d-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d99d-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d99d-120">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="8d99d-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="8d99d-121">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8d99d-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d99d-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d99d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d99d-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d99d-123">See also</span></span>

- [<span data-ttu-id="8d99d-124">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8d99d-124">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="8d99d-125">AssemblyBindInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="8d99d-125">AssemblyBindInfo Structure</span></span>](assemblybindinfo-structure.md)
- [<span data-ttu-id="8d99d-126">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d99d-126">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="8d99d-127">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d99d-127">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="8d99d-128">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d99d-128">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
