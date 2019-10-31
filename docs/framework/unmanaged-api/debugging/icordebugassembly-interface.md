---
title: ICorDebugAssembly (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
ms.openlocfilehash: dea3231e3bbb361b56254756c6d99b115f73e792
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133970"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="fbeb2-102">ICorDebugAssembly (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fbeb2-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="fbeb2-103">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fbeb2-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fbeb2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="fbeb2-104">Methods</span></span>  
  
|<span data-ttu-id="fbeb2-105">Método</span><span class="sxs-lookup"><span data-stu-id="fbeb2-105">Method</span></span>|<span data-ttu-id="fbeb2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbeb2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fbeb2-107">EnumerateModules (método)</span><span class="sxs-lookup"><span data-stu-id="fbeb2-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="fbeb2-108">Obtiene un enumerador para los módulos incluidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fbeb2-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="fbeb2-109">GetAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="fbeb2-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="fbeb2-110">Obtiene un puntero de interfaz al dominio de aplicación que contiene esta instancia de `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="fbeb2-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="fbeb2-111">GetCodeBase (método)</span><span class="sxs-lookup"><span data-stu-id="fbeb2-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="fbeb2-112">No se implementa en la versión actual del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fbeb2-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="fbeb2-113">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="fbeb2-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="fbeb2-114">Obtiene el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fbeb2-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="fbeb2-115">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="fbeb2-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="fbeb2-116">Obtiene la instancia de ICorDebugProcess en la que se ejecuta el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fbeb2-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbeb2-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fbeb2-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fbeb2-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="fbeb2-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbeb2-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fbeb2-119">Requirements</span></span>  
 <span data-ttu-id="fbeb2-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbeb2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbeb2-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fbeb2-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fbeb2-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbeb2-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbeb2-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbeb2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbeb2-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbeb2-124">See also</span></span>

- [<span data-ttu-id="fbeb2-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="fbeb2-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
