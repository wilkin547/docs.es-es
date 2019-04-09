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
ms.openlocfilehash: 3dd60defc1c003fa4b235ddcb0a78b9a819b1b0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198028"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="f7c60-102">Interfaz ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="f7c60-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="f7c60-103">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f7c60-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f7c60-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f7c60-104">Methods</span></span>  
  
|<span data-ttu-id="f7c60-105">Método</span><span class="sxs-lookup"><span data-stu-id="f7c60-105">Method</span></span>|<span data-ttu-id="f7c60-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7c60-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f7c60-107">Método EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="f7c60-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="f7c60-108">Obtiene un enumerador para los módulos incluidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f7c60-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="f7c60-109">Método GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="f7c60-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="f7c60-110">Obtiene un puntero de interfaz al dominio de aplicación que contiene esta `ICorDebugAssembly` instancia.</span><span class="sxs-lookup"><span data-stu-id="f7c60-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="f7c60-111">Método GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="f7c60-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="f7c60-112">No se implementa en la versión actual de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7c60-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="f7c60-113">Método GetName</span><span class="sxs-lookup"><span data-stu-id="f7c60-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="f7c60-114">Obtiene el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f7c60-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="f7c60-115">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="f7c60-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="f7c60-116">Obtiene la instancia de ICorDebugProcess en que se ejecuta el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f7c60-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7c60-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7c60-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7c60-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f7c60-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7c60-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7c60-119">Requirements</span></span>  
 <span data-ttu-id="f7c60-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7c60-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7c60-121">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7c60-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7c60-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7c60-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f7c60-123">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f7c60-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f7c60-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7c60-124">See also</span></span>

- [<span data-ttu-id="f7c60-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f7c60-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
