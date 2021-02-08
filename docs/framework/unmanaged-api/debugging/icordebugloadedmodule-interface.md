---
description: 'Más información acerca de: interfaz ICorDebugLoadedModule'
title: Interfaz de ICorDebugLoadedModule
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
ms.openlocfilehash: 6a1b466a9d2d7781fad7ac2bc8c24f0b2a5c23e0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801233"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="13177-103">Interfaz de ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="13177-103">ICorDebugLoadedModule Interface</span></span>

<span data-ttu-id="13177-104">Proporciona información acerca de un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="13177-104">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13177-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="13177-105">Methods</span></span>  
  
|<span data-ttu-id="13177-106">Método</span><span class="sxs-lookup"><span data-stu-id="13177-106">Method</span></span>|<span data-ttu-id="13177-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="13177-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13177-108">GetBaseAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="13177-108">GetBaseAddress Method</span></span>](icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="13177-109">Obtiene la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="13177-109">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="13177-110">Método GetName</span><span class="sxs-lookup"><span data-stu-id="13177-110">GetName Method</span></span>](icordebugloadedmodule-getname-method.md)|<span data-ttu-id="13177-111">Obtiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="13177-111">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="13177-112">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="13177-112">GetSize Method</span></span>](icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="13177-113">Obtiene el tamaño, en bytes, del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="13177-113">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13177-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="13177-114">Remarks</span></span>  

 <span data-ttu-id="13177-115">La interfaz `ICorDebugLoadedModule` es implementada por un depurador y utiliza por interfaces de depuración de CLR para obtener información acerca del módulo cargado desde el depurador.</span><span class="sxs-lookup"><span data-stu-id="13177-115">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13177-116">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="13177-116">This interface is available with .NET Native only.</span></span> <span data-ttu-id="13177-117">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="13177-117">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13177-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13177-118">Requirements</span></span>  

 <span data-ttu-id="13177-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13177-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13177-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13177-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13177-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13177-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13177-122">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13177-122">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13177-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="13177-123">See also</span></span>

- [<span data-ttu-id="13177-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="13177-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="13177-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="13177-125">Debugging</span></span>](index.md)
