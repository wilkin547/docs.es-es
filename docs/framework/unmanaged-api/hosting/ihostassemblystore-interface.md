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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4067c1fbcf99c903c892eaec58262d95569114b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173425"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="adbf6-102">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="adbf6-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="adbf6-103">Proporciona métodos que permiten a un host cargar ensamblados y módulos con independencia de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="adbf6-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="adbf6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="adbf6-104">Methods</span></span>  
  
|<span data-ttu-id="adbf6-105">Método</span><span class="sxs-lookup"><span data-stu-id="adbf6-105">Method</span></span>|<span data-ttu-id="adbf6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="adbf6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="adbf6-107">Método ProvideAssembly</span><span class="sxs-lookup"><span data-stu-id="adbf6-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="adbf6-108">Obtiene una referencia a un ensamblado que no hace referencia el [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) devueltos por una llamada a [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="adbf6-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="adbf6-109">Método ProvideModule</span><span class="sxs-lookup"><span data-stu-id="adbf6-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="adbf6-110">Resuelve un módulo dentro de un ensamblado o un archivo de recursos (no incrustado) vinculados.</span><span class="sxs-lookup"><span data-stu-id="adbf6-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adbf6-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="adbf6-111">Remarks</span></span>  
 `IHostAssemblyStore` <span data-ttu-id="adbf6-112">Proporciona una manera para un host cargar ensamblados eficazmente basándose en la identidad del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="adbf6-112">provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="adbf6-113">El host carga ensamblados devolviendo `IStream` instancias que apuntan directamente a los bytes.</span><span class="sxs-lookup"><span data-stu-id="adbf6-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="adbf6-114">El CLR para determinar si se ha implementado un host `IHostAssemblyStore` mediante una llamada a `IHostAssemblyManager::GetNonHostAssemblyStores` tras la inicialización.</span><span class="sxs-lookup"><span data-stu-id="adbf6-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="adbf6-115">Esto permite al host, por ejemplo, para controlar el enlace a los ensamblados de usuario, sino que se basarán en el tiempo de ejecución para enlazar a ensamblados de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="adbf6-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adbf6-116">Al proporcionar una implementación de `IHostAssemblyStore`, el host especifica su intento de resolver todos los ensamblados que no hace referencia el `ICLRAssemblyReferenceList` devuelto desde `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="adbf6-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adbf6-117">La versión 2.0 de .NET Framework no proporciona una forma para el host cargar la imagen nativa de un ensamblado, tal como lo proporciona el [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utilidad.</span><span class="sxs-lookup"><span data-stu-id="adbf6-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adbf6-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="adbf6-118">Requirements</span></span>  
 <span data-ttu-id="adbf6-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adbf6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adbf6-120">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="adbf6-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="adbf6-121">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="adbf6-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="adbf6-122">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="adbf6-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="adbf6-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="adbf6-123">See also</span></span>

- [<span data-ttu-id="adbf6-124">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="adbf6-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="adbf6-125">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="adbf6-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="adbf6-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="adbf6-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
