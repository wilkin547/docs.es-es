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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2b802845e36e818a962484c1fea09cbcc1ceefd
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974580"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="d196a-102">ICorDebugAssembly (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d196a-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="d196a-103">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d196a-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d196a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d196a-104">Methods</span></span>  
  
|<span data-ttu-id="d196a-105">Método</span><span class="sxs-lookup"><span data-stu-id="d196a-105">Method</span></span>|<span data-ttu-id="d196a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d196a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d196a-107">EnumerateModules (método)</span><span class="sxs-lookup"><span data-stu-id="d196a-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="d196a-108">Obtiene un enumerador para los módulos incluidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d196a-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="d196a-109">GetAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="d196a-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="d196a-110">Obtiene un puntero de interfaz al dominio de aplicación que contiene esta `ICorDebugAssembly` instancia.</span><span class="sxs-lookup"><span data-stu-id="d196a-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="d196a-111">GetCodeBase (método)</span><span class="sxs-lookup"><span data-stu-id="d196a-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="d196a-112">No se implementa en la versión actual de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d196a-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="d196a-113">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="d196a-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="d196a-114">Obtiene el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d196a-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="d196a-115">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="d196a-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="d196a-116">Obtiene la instancia de ICorDebugProcess en que se ejecuta el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d196a-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d196a-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d196a-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d196a-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="d196a-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d196a-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d196a-119">Requirements</span></span>  
 <span data-ttu-id="d196a-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d196a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d196a-121">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d196a-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d196a-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d196a-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d196a-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d196a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d196a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d196a-124">See also</span></span>
- [<span data-ttu-id="d196a-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d196a-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
