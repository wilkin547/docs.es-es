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
ms.openlocfilehash: d9e2236b944137de82bb056820f81014febfcc5f
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894897"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="6eb3b-102">Interfaz ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="6eb3b-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="6eb3b-103">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6eb3b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6eb3b-104">Methods</span></span>  
  
|<span data-ttu-id="6eb3b-105">Método</span><span class="sxs-lookup"><span data-stu-id="6eb3b-105">Method</span></span>|<span data-ttu-id="6eb3b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6eb3b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6eb3b-107">Método EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="6eb3b-107">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="6eb3b-108">Obtiene un enumerador para los módulos incluidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="6eb3b-109">Método GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="6eb3b-109">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="6eb3b-110">Obtiene un puntero de interfaz al dominio de aplicación que contiene `ICorDebugAssembly` esta instancia.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="6eb3b-111">Método GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="6eb3b-111">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="6eb3b-112">No se implementa en la versión actual del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="6eb3b-113">Método GetName</span><span class="sxs-lookup"><span data-stu-id="6eb3b-113">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="6eb3b-114">Obtiene el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="6eb3b-115">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="6eb3b-115">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="6eb3b-116">Obtiene la instancia de ICorDebugProcess en la que se ejecuta el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6eb3b-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6eb3b-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6eb3b-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="6eb3b-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6eb3b-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6eb3b-119">Requirements</span></span>  
 <span data-ttu-id="6eb3b-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6eb3b-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6eb3b-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6eb3b-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6eb3b-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6eb3b-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6eb3b-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6eb3b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eb3b-124">Consulta también</span><span class="sxs-lookup"><span data-stu-id="6eb3b-124">See also</span></span>

- [<span data-ttu-id="6eb3b-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="6eb3b-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
