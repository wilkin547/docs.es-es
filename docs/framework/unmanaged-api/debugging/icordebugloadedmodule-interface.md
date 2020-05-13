---
title: Interfaz de ICorDebugLoadedModule
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
ms.openlocfilehash: d9b8245d8c37867971aa48ed3befb9cf22bd5b04
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210168"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="ddf7d-102">Interfaz de ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="ddf7d-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="ddf7d-103">Proporciona información acerca de un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="ddf7d-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ddf7d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ddf7d-104">Methods</span></span>  
  
|<span data-ttu-id="ddf7d-105">Método</span><span class="sxs-lookup"><span data-stu-id="ddf7d-105">Method</span></span>|<span data-ttu-id="ddf7d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddf7d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ddf7d-107">GetBaseAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="ddf7d-107">GetBaseAddress Method</span></span>](icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="ddf7d-108">Obtiene la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="ddf7d-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="ddf7d-109">Método GetName</span><span class="sxs-lookup"><span data-stu-id="ddf7d-109">GetName Method</span></span>](icordebugloadedmodule-getname-method.md)|<span data-ttu-id="ddf7d-110">Obtiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="ddf7d-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="ddf7d-111">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="ddf7d-111">GetSize Method</span></span>](icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="ddf7d-112">Obtiene el tamaño, en bytes, del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="ddf7d-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddf7d-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ddf7d-113">Remarks</span></span>  
 <span data-ttu-id="ddf7d-114">La interfaz `ICorDebugLoadedModule` es implementada por un depurador y utiliza por interfaces de depuración de CLR para obtener información acerca del módulo cargado desde el depurador.</span><span class="sxs-lookup"><span data-stu-id="ddf7d-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ddf7d-115">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ddf7d-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="ddf7d-116">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="ddf7d-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddf7d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ddf7d-117">Requirements</span></span>  
 <span data-ttu-id="ddf7d-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddf7d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddf7d-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ddf7d-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ddf7d-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddf7d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddf7d-121">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddf7d-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddf7d-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ddf7d-122">See also</span></span>

- [<span data-ttu-id="ddf7d-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ddf7d-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ddf7d-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="ddf7d-124">Debugging</span></span>](index.md)
