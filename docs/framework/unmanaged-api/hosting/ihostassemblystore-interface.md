---
title: IHostAssemblyStore (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore
helpviewer_keywords: IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 284afbe73bea28a0aafe8d5e9e030c43be94aea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="47402-102">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="47402-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="47402-103">Proporciona métodos que permiten a un host cargar ensamblados y módulos con independencia de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="47402-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="47402-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="47402-104">Methods</span></span>  
  
|<span data-ttu-id="47402-105">Método</span><span class="sxs-lookup"><span data-stu-id="47402-105">Method</span></span>|<span data-ttu-id="47402-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="47402-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="47402-107">ProvideAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="47402-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="47402-108">Obtiene una referencia a un ensamblado que no hace referencia la [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) devuelto desde una llamada a [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="47402-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="47402-109">ProvideModule (método)</span><span class="sxs-lookup"><span data-stu-id="47402-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="47402-110">Resuelve un módulo dentro de un ensamblado o un archivo de recursos (no incrustado) vinculados.</span><span class="sxs-lookup"><span data-stu-id="47402-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47402-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47402-111">Remarks</span></span>  
 <span data-ttu-id="47402-112">`IHostAssemblyStore`Proporciona una manera para que un host cargar los ensamblados eficazmente basándose en la identidad del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="47402-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="47402-113">El host carga los ensamblados devolviendo `IStream` instancias que apuntan directamente a los bytes.</span><span class="sxs-lookup"><span data-stu-id="47402-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="47402-114">CLR determina si un host ha implementado `IHostAssemblyStore` mediante una llamada a `IHostAssemblyManager::GetNonHostAssemblyStores` en la inicialización.</span><span class="sxs-lookup"><span data-stu-id="47402-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="47402-115">Esto permite al host, por ejemplo, para controlar el enlace a los ensamblados de usuario, sino que se basarán en el tiempo de ejecución para enlazar a ensamblados de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47402-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47402-116">Para proporcionar una implementación de `IHostAssemblyStore`, el host especifica su intento de resolver todos los ensamblados que no tienen referencias en el `ICLRAssemblyReferenceList` devuelto desde `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="47402-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47402-117">La versión 2.0 de .NET Framework no proporciona una manera para que el host cargar la imagen nativa de un ensamblado, proporcionados por el [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utilidad.</span><span class="sxs-lookup"><span data-stu-id="47402-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47402-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47402-118">Requirements</span></span>  
 <span data-ttu-id="47402-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47402-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47402-120">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="47402-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="47402-121">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="47402-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47402-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47402-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47402-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="47402-123">See Also</span></span>  
 [<span data-ttu-id="47402-124">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47402-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="47402-125">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47402-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="47402-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="47402-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
