---
title: Interfaz ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca77360c36ff2cdce7ee47d5c3883dd824c6cef8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959320"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="cf6b1-102">Interfaz ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="cf6b1-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="cf6b1-103">Extiende lógicamente la interfaz ICorDebugAssembly para proporcionar compatibilidad con los ensamblados de contenedor y sus ensamblados incluidos.</span><span class="sxs-lookup"><span data-stu-id="cf6b1-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cf6b1-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="cf6b1-104">Methods</span></span>  
  
|<span data-ttu-id="cf6b1-105">Método</span><span class="sxs-lookup"><span data-stu-id="cf6b1-105">Method</span></span>|<span data-ttu-id="cf6b1-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cf6b1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cf6b1-107">EnumerateContainedAssemblies (método)</span><span class="sxs-lookup"><span data-stu-id="cf6b1-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="cf6b1-108">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cf6b1-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="cf6b1-109">GetContainerAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="cf6b1-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="cf6b1-110">Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="cf6b1-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf6b1-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf6b1-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cf6b1-112">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cf6b1-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="cf6b1-113">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="cf6b1-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf6b1-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf6b1-114">Requirements</span></span>  
 <span data-ttu-id="cf6b1-115">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf6b1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf6b1-116">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="cf6b1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf6b1-117">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf6b1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf6b1-118">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf6b1-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf6b1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf6b1-119">See also</span></span>

- [<span data-ttu-id="cf6b1-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cf6b1-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="cf6b1-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="cf6b1-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
