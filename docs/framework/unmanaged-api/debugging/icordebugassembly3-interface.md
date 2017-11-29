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
ms.openlocfilehash: b9ed476746e627be987e6307bd367f0d16374de5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="5e47c-102">Interfaz ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="5e47c-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="5e47c-103">Extiende lógicamente la ICorDebugAssembly (interfaz) para proporcionar compatibilidad con los ensamblados de contenedor y sus contenidos.</span><span class="sxs-lookup"><span data-stu-id="5e47c-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e47c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5e47c-104">Methods</span></span>  
  
|<span data-ttu-id="5e47c-105">Método</span><span class="sxs-lookup"><span data-stu-id="5e47c-105">Method</span></span>|<span data-ttu-id="5e47c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e47c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e47c-107">Método EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="5e47c-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="5e47c-108">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5e47c-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="5e47c-109">Método GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="5e47c-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="5e47c-110">Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="5e47c-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e47c-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e47c-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e47c-112">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5e47c-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="5e47c-113">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="5e47c-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e47c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e47c-114">Requirements</span></span>  
 <span data-ttu-id="5e47c-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e47c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e47c-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e47c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e47c-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e47c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e47c-118">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e47c-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e47c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e47c-119">See Also</span></span>  
 [<span data-ttu-id="5e47c-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="5e47c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5e47c-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="5e47c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
