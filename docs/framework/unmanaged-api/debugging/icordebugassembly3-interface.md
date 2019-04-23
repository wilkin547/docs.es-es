---
title: Interfaz ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eecb135e034c3565e805ea776115579488b2a4d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210313"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="7cdce-102">Interfaz ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="7cdce-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="7cdce-103">Extiende lógicamente la ICorDebugAssembly (interfaz) para proporcionar compatibilidad para los ensamblados de contenedor y los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="7cdce-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7cdce-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7cdce-104">Methods</span></span>  
  
|<span data-ttu-id="7cdce-105">Método</span><span class="sxs-lookup"><span data-stu-id="7cdce-105">Method</span></span>|<span data-ttu-id="7cdce-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7cdce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7cdce-107">EnumerateContainedAssemblies (método)</span><span class="sxs-lookup"><span data-stu-id="7cdce-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="7cdce-108">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7cdce-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="7cdce-109">GetContainerAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="7cdce-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="7cdce-110">Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="7cdce-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cdce-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7cdce-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7cdce-112">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7cdce-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="7cdce-113">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="7cdce-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cdce-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7cdce-114">Requirements</span></span>  
 <span data-ttu-id="7cdce-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cdce-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cdce-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7cdce-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7cdce-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cdce-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cdce-118">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cdce-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cdce-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cdce-119">See also</span></span>

- [<span data-ttu-id="7cdce-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7cdce-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7cdce-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="7cdce-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
