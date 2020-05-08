---
title: Interfaz ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: 67707092c80b0e07aa284336c426aba09ff991af
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894824"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="ad505-102">Interfaz ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="ad505-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="ad505-103">Extiende la interfaz ICorDebugAssembly de manera lógica para proporcionar compatibilidad con los ensamblados de contenedor y con los ensamblados que estos contienen.</span><span class="sxs-lookup"><span data-stu-id="ad505-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad505-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ad505-104">Methods</span></span>  
  
|<span data-ttu-id="ad505-105">Método</span><span class="sxs-lookup"><span data-stu-id="ad505-105">Method</span></span>|<span data-ttu-id="ad505-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad505-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad505-107">Método EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="ad505-107">EnumerateContainedAssemblies Method</span></span>](icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="ad505-108">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ad505-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="ad505-109">Método GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="ad505-109">GetContainerAssembly Method</span></span>](icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="ad505-110">Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="ad505-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad505-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ad505-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad505-112">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ad505-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="ad505-113">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="ad505-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad505-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad505-114">Requirements</span></span>  
 <span data-ttu-id="ad505-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad505-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad505-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad505-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad505-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad505-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad505-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad505-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad505-119">Consulta también</span><span class="sxs-lookup"><span data-stu-id="ad505-119">See also</span></span>

- [<span data-ttu-id="ad505-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ad505-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ad505-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="ad505-121">Debugging</span></span>](index.md)
