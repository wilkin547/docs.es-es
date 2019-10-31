---
title: IHostAssemblyStore (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
ms.openlocfilehash: d7475e2423d4dc6f57e8928514d7991169eef232
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124501"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="97ac8-102">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="97ac8-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="97ac8-103">Proporciona métodos que permiten a un host cargar ensamblados y módulos independientemente del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="97ac8-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97ac8-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="97ac8-104">Methods</span></span>  
  
|<span data-ttu-id="97ac8-105">Método</span><span class="sxs-lookup"><span data-stu-id="97ac8-105">Method</span></span>|<span data-ttu-id="97ac8-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="97ac8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="97ac8-107">ProvideAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="97ac8-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="97ac8-108">Obtiene una referencia a un ensamblado al que no hace referencia el [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) devuelto de una llamada a [IHostAssemblyManager:: GetNonHostStoreAssemblies (](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="97ac8-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="97ac8-109">ProvideModule (método)</span><span class="sxs-lookup"><span data-stu-id="97ac8-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="97ac8-110">Resuelve un módulo dentro de un ensamblado o un archivo de recursos vinculado (no incrustado).</span><span class="sxs-lookup"><span data-stu-id="97ac8-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97ac8-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="97ac8-111">Remarks</span></span>  
 <span data-ttu-id="97ac8-112">`IHostAssemblyStore` proporciona una forma para que un host cargue los ensamblados de forma eficaz en función de la identidad del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="97ac8-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="97ac8-113">El host carga los ensamblados devolviendo `IStream` instancias que apuntan directamente a los bytes.</span><span class="sxs-lookup"><span data-stu-id="97ac8-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="97ac8-114">CLR determina si un host ha implementado `IHostAssemblyStore` llamando a `IHostAssemblyManager::GetNonHostAssemblyStores` tras la inicialización.</span><span class="sxs-lookup"><span data-stu-id="97ac8-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="97ac8-115">Esto permite al host controlar el enlace a ensamblados de usuario, pero basarse en el tiempo de ejecución para enlazar a ensamblados de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="97ac8-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97ac8-116">Al proporcionar una implementación de `IHostAssemblyStore`, el host especifica su intención de resolver todos los ensamblados a los que no hace referencia el `ICLRAssemblyReferenceList` devuelto desde `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="97ac8-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97ac8-117">La versión 2,0 de .NET Framework no proporciona una manera para que el host cargue la imagen nativa de un ensamblado, tal y como lo proporciona la utilidad del [generador de imágenes nativas (Ngen. exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) .</span><span class="sxs-lookup"><span data-stu-id="97ac8-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97ac8-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="97ac8-118">Requirements</span></span>  
 <span data-ttu-id="97ac8-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97ac8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97ac8-120">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="97ac8-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97ac8-121">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="97ac8-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97ac8-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97ac8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97ac8-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="97ac8-123">See also</span></span>

- [<span data-ttu-id="97ac8-124">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="97ac8-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="97ac8-125">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="97ac8-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="97ac8-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="97ac8-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
