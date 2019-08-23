---
title: Interfaz ICorDebugAssembly
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 426269d14992ae0f1f8c02619b259cfdd4bcbf8f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959437"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="c9cd4-102">Interfaz ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="c9cd4-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="c9cd4-103">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c9cd4-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c9cd4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c9cd4-104">Methods</span></span>  
  
|<span data-ttu-id="c9cd4-105">Método</span><span class="sxs-lookup"><span data-stu-id="c9cd4-105">Method</span></span>|<span data-ttu-id="c9cd4-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c9cd4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c9cd4-107">EnumerateModules (método)</span><span class="sxs-lookup"><span data-stu-id="c9cd4-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="c9cd4-108">Obtiene un enumerador para los módulos incluidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c9cd4-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="c9cd4-109">GetAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="c9cd4-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="c9cd4-110">Obtiene un puntero de interfaz al dominio de aplicación que contiene `ICorDebugAssembly` esta instancia.</span><span class="sxs-lookup"><span data-stu-id="c9cd4-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="c9cd4-111">GetCodeBase (método)</span><span class="sxs-lookup"><span data-stu-id="c9cd4-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="c9cd4-112">No se implementa en la versión actual del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c9cd4-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="c9cd4-113">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="c9cd4-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="c9cd4-114">Obtiene el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c9cd4-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="c9cd4-115">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="c9cd4-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="c9cd4-116">Obtiene la instancia de ICorDebugProcess en la que se ejecuta el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c9cd4-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9cd4-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c9cd4-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9cd4-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c9cd4-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9cd4-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9cd4-119">Requirements</span></span>  
 <span data-ttu-id="c9cd4-120">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9cd4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9cd4-121">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="c9cd4-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9cd4-122">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9cd4-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9cd4-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9cd4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9cd4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9cd4-124">See also</span></span>

- [<span data-ttu-id="c9cd4-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c9cd4-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
