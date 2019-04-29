---
title: Interfaz ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eecb135e034c3565e805ea776115579488b2a4d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645466"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="bf9c6-102">Interfaz ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="bf9c6-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="bf9c6-103">Extiende lógicamente la ICorDebugAssembly (interfaz) para proporcionar compatibilidad para los ensamblados de contenedor y los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="bf9c6-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf9c6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="bf9c6-104">Methods</span></span>  
  
|<span data-ttu-id="bf9c6-105">Método</span><span class="sxs-lookup"><span data-stu-id="bf9c6-105">Method</span></span>|<span data-ttu-id="bf9c6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf9c6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf9c6-107">EnumerateContainedAssemblies (método)</span><span class="sxs-lookup"><span data-stu-id="bf9c6-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="bf9c6-108">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bf9c6-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="bf9c6-109">GetContainerAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="bf9c6-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="bf9c6-110">Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="bf9c6-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf9c6-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf9c6-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf9c6-112">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bf9c6-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="bf9c6-113">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="bf9c6-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf9c6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf9c6-114">Requirements</span></span>  
 <span data-ttu-id="bf9c6-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf9c6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf9c6-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf9c6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf9c6-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf9c6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf9c6-118">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf9c6-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf9c6-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf9c6-119">See also</span></span>

- [<span data-ttu-id="bf9c6-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bf9c6-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="bf9c6-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="bf9c6-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
