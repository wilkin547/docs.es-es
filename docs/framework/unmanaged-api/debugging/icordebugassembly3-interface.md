---
title: Interfaz ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eecb135e034c3565e805ea776115579488b2a4d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210313"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="66989-102">Interfaz ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="66989-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="66989-103">Extiende lógicamente la ICorDebugAssembly (interfaz) para proporcionar compatibilidad para los ensamblados de contenedor y los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="66989-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="66989-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="66989-104">Methods</span></span>  
  
|<span data-ttu-id="66989-105">Método</span><span class="sxs-lookup"><span data-stu-id="66989-105">Method</span></span>|<span data-ttu-id="66989-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="66989-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="66989-107">Método EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="66989-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="66989-108">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="66989-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="66989-109">Método GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="66989-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="66989-110">Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="66989-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66989-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="66989-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66989-112">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="66989-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="66989-113">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="66989-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66989-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66989-114">Requirements</span></span>  
 <span data-ttu-id="66989-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66989-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66989-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66989-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66989-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66989-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="66989-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="66989-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="66989-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="66989-119">See also</span></span>

- [<span data-ttu-id="66989-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="66989-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="66989-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="66989-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
