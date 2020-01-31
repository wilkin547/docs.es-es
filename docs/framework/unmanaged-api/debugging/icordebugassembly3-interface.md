---
title: ICorDebugAssembly3 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: deb300ced2ff7a116bd443c9a7b10dcc0b7955ac
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784529"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="1506a-102">ICorDebugAssembly3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1506a-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="1506a-103">Extiende la interfaz ICorDebugAssembly de manera lógica para proporcionar compatibilidad con los ensamblados de contenedor y con los ensamblados que estos contienen.</span><span class="sxs-lookup"><span data-stu-id="1506a-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1506a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1506a-104">Methods</span></span>  
  
|<span data-ttu-id="1506a-105">Método</span><span class="sxs-lookup"><span data-stu-id="1506a-105">Method</span></span>|<span data-ttu-id="1506a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1506a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1506a-107">EnumerateContainedAssemblies (método)</span><span class="sxs-lookup"><span data-stu-id="1506a-107">EnumerateContainedAssemblies Method</span></span>](icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="1506a-108">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1506a-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="1506a-109">GetContainerAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="1506a-109">GetContainerAssembly Method</span></span>](icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="1506a-110">Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="1506a-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1506a-111">Notas</span><span class="sxs-lookup"><span data-stu-id="1506a-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1506a-112">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1506a-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="1506a-113">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="1506a-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1506a-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="1506a-114">Requirements</span></span>  
 <span data-ttu-id="1506a-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1506a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1506a-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1506a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1506a-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1506a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1506a-118">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1506a-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1506a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1506a-119">See also</span></span>

- [<span data-ttu-id="1506a-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1506a-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1506a-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="1506a-121">Debugging</span></span>](index.md)
