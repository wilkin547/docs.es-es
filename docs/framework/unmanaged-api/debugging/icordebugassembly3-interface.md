---
title: Interfaz ICorDebugAssembly3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e581b4256da2ecc19a8b97520e0e70fef972b549
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="3abb2-102">Interfaz ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="3abb2-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="3abb2-103">Extiende lógicamente la ICorDebugAssembly (interfaz) para proporcionar compatibilidad con los ensamblados de contenedor y sus contenidos.</span><span class="sxs-lookup"><span data-stu-id="3abb2-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3abb2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3abb2-104">Methods</span></span>  
  
|<span data-ttu-id="3abb2-105">Método</span><span class="sxs-lookup"><span data-stu-id="3abb2-105">Method</span></span>|<span data-ttu-id="3abb2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3abb2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3abb2-107">EnumerateContainedAssemblies (método)</span><span class="sxs-lookup"><span data-stu-id="3abb2-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="3abb2-108">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3abb2-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="3abb2-109">GetContainerAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="3abb2-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="3abb2-110">Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="3abb2-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3abb2-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3abb2-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3abb2-112">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3abb2-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="3abb2-113">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="3abb2-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3abb2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3abb2-114">Requirements</span></span>  
 <span data-ttu-id="3abb2-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3abb2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3abb2-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3abb2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3abb2-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3abb2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3abb2-118">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3abb2-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3abb2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3abb2-119">See Also</span></span>  
 [<span data-ttu-id="3abb2-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3abb2-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="3abb2-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="3abb2-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
