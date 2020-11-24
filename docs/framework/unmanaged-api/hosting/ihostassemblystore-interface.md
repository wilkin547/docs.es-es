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
ms.openlocfilehash: 4b2fed963d2d0ebec54e5f7a4d95cba26c1bac1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680959"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="f6f04-102">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6f04-102">IHostAssemblyStore Interface</span></span>

<span data-ttu-id="f6f04-103">Proporciona métodos que permiten a un host cargar ensamblados y módulos independientemente del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f6f04-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f6f04-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f6f04-104">Methods</span></span>  
  
|<span data-ttu-id="f6f04-105">Método</span><span class="sxs-lookup"><span data-stu-id="f6f04-105">Method</span></span>|<span data-ttu-id="f6f04-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6f04-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6f04-107">Método ProvideAssembly</span><span class="sxs-lookup"><span data-stu-id="f6f04-107">ProvideAssembly Method</span></span>](ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="f6f04-108">Obtiene una referencia a un ensamblado al que no hace referencia el [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) devuelto de una llamada a [IHostAssemblyManager:: GetNonHostStoreAssemblies (](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="f6f04-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="f6f04-109">Método ProvideModule</span><span class="sxs-lookup"><span data-stu-id="f6f04-109">ProvideModule Method</span></span>](ihostassemblystore-providemodule-method.md)|<span data-ttu-id="f6f04-110">Resuelve un módulo dentro de un ensamblado o un archivo de recursos vinculado (no incrustado).</span><span class="sxs-lookup"><span data-stu-id="f6f04-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6f04-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6f04-111">Remarks</span></span>  

 <span data-ttu-id="f6f04-112">`IHostAssemblyStore` proporciona una forma para que un host cargue los ensamblados de forma eficaz en función de la identidad del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f6f04-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="f6f04-113">El host carga los ensamblados devolviendo `IStream` instancias que apuntan directamente a los bytes.</span><span class="sxs-lookup"><span data-stu-id="f6f04-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="f6f04-114">CLR determina si un host se ha implementado `IHostAssemblyStore` mediante una llamada a en la `IHostAssemblyManager::GetNonHostAssemblyStores` inicialización.</span><span class="sxs-lookup"><span data-stu-id="f6f04-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="f6f04-115">Esto permite al host controlar el enlace a ensamblados de usuario, pero basarse en el tiempo de ejecución para enlazar a ensamblados de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f6f04-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6f04-116">Al proporcionar una implementación de `IHostAssemblyStore` , el host especifica su intención de resolver todos los ensamblados a los que no hace referencia el `ICLRAssemblyReferenceList` devuelto de `IHostAssemblyManager::GetNonHostStoreAssemblies` .</span><span class="sxs-lookup"><span data-stu-id="f6f04-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6f04-117">La versión 2,0 de .NET Framework no proporciona una manera para que el host cargue la imagen nativa de un ensamblado, tal y como lo proporciona la utilidad de [generación de imágenes nativas (Ngen.exe)](../../tools/ngen-exe-native-image-generator.md) .</span><span class="sxs-lookup"><span data-stu-id="f6f04-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6f04-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6f04-118">Requirements</span></span>  

 <span data-ttu-id="f6f04-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6f04-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6f04-120">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f6f04-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6f04-121">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6f04-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6f04-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6f04-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f04-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f6f04-123">See also</span></span>

- [<span data-ttu-id="f6f04-124">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6f04-124">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="f6f04-125">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6f04-125">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="f6f04-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="f6f04-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
