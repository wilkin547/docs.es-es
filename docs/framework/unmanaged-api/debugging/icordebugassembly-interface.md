---
title: ICorDebugAssembly (Interfaz1)
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
ms.openlocfilehash: 8a6776467eb9f5eaaacadb2908de17fc277e495b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569185"
---
# <a name="icordebugassembly-interface1"></a><span data-ttu-id="3c7c0-102">ICorDebugAssembly (Interfaz1)</span><span class="sxs-lookup"><span data-stu-id="3c7c0-102">ICorDebugAssembly Interface1</span></span>
<span data-ttu-id="3c7c0-103">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3c7c0-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3c7c0-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3c7c0-104">Methods</span></span>  
  
|<span data-ttu-id="3c7c0-105">Método</span><span class="sxs-lookup"><span data-stu-id="3c7c0-105">Method</span></span>|<span data-ttu-id="3c7c0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c7c0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3c7c0-107">EnumerateModules (método)</span><span class="sxs-lookup"><span data-stu-id="3c7c0-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="3c7c0-108">Obtiene un enumerador para los módulos incluidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3c7c0-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="3c7c0-109">GetAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="3c7c0-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="3c7c0-110">Obtiene un puntero de interfaz al dominio de aplicación que contiene esta `ICorDebugAssembly` instancia.</span><span class="sxs-lookup"><span data-stu-id="3c7c0-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="3c7c0-111">GetCodeBase (método)</span><span class="sxs-lookup"><span data-stu-id="3c7c0-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="3c7c0-112">No se implementa en la versión actual de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3c7c0-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="3c7c0-113">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="3c7c0-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="3c7c0-114">Obtiene el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3c7c0-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="3c7c0-115">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="3c7c0-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="3c7c0-116">Obtiene la instancia de ICorDebugProcess en que se ejecuta el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3c7c0-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c7c0-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c7c0-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c7c0-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3c7c0-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c7c0-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c7c0-119">Requirements</span></span>  
 <span data-ttu-id="3c7c0-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c7c0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c7c0-121">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c7c0-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c7c0-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c7c0-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c7c0-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c7c0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c7c0-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c7c0-124">See also</span></span>
- [<span data-ttu-id="3c7c0-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3c7c0-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
