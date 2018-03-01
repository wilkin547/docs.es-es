---
title: ICorDebugAssembly Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6331c00c2be0805afb56028e9e1a13cd11168cf1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassembly-interface1"></a><span data-ttu-id="681b5-102">ICorDebugAssembly Interfaz1</span><span class="sxs-lookup"><span data-stu-id="681b5-102">ICorDebugAssembly Interface1</span></span>
<span data-ttu-id="681b5-103">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="681b5-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="681b5-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="681b5-104">Methods</span></span>  
  
|<span data-ttu-id="681b5-105">Método</span><span class="sxs-lookup"><span data-stu-id="681b5-105">Method</span></span>|<span data-ttu-id="681b5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="681b5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="681b5-107">EnumerateModules (método)</span><span class="sxs-lookup"><span data-stu-id="681b5-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="681b5-108">Obtiene un enumerador para los módulos incluidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="681b5-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="681b5-109">GetAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="681b5-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="681b5-110">Obtiene un puntero de interfaz al dominio de aplicación que contiene esta `ICorDebugAssembly` instancia.</span><span class="sxs-lookup"><span data-stu-id="681b5-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="681b5-111">GetCodeBase (método)</span><span class="sxs-lookup"><span data-stu-id="681b5-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="681b5-112">No se implementa en la versión actual de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="681b5-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="681b5-113">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="681b5-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="681b5-114">Obtiene el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="681b5-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="681b5-115">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="681b5-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="681b5-116">Obtiene la instancia de ICorDebugProcess en que se ejecuta el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="681b5-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="681b5-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="681b5-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="681b5-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="681b5-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="681b5-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="681b5-119">Requirements</span></span>  
 <span data-ttu-id="681b5-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="681b5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="681b5-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="681b5-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="681b5-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="681b5-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="681b5-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="681b5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="681b5-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="681b5-124">See Also</span></span>  
 [<span data-ttu-id="681b5-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="681b5-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
