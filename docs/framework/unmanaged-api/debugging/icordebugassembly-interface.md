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
ms.openlocfilehash: ecd4ad31b8dad55e9538642a4dc652341bc84b97
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784674"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="f561c-102">Interfaz ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="f561c-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="f561c-103">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f561c-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f561c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f561c-104">Methods</span></span>  
  
|<span data-ttu-id="f561c-105">Método</span><span class="sxs-lookup"><span data-stu-id="f561c-105">Method</span></span>|<span data-ttu-id="f561c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f561c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f561c-107">EnumerateModules (método)</span><span class="sxs-lookup"><span data-stu-id="f561c-107">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="f561c-108">Obtiene un enumerador para los módulos incluidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f561c-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="f561c-109">GetAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="f561c-109">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="f561c-110">Obtiene un puntero de interfaz al dominio de aplicación que contiene esta instancia de `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="f561c-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="f561c-111">GetCodeBase (método)</span><span class="sxs-lookup"><span data-stu-id="f561c-111">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="f561c-112">No se implementa en la versión actual del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f561c-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="f561c-113">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="f561c-113">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="f561c-114">Obtiene el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f561c-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="f561c-115">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="f561c-115">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="f561c-116">Obtiene la instancia de ICorDebugProcess en la que se ejecuta el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f561c-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f561c-117">Notas</span><span class="sxs-lookup"><span data-stu-id="f561c-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f561c-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f561c-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f561c-119">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f561c-119">Requirements</span></span>  
 <span data-ttu-id="f561c-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f561c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f561c-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f561c-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f561c-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f561c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f561c-123">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f561c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f561c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f561c-124">See also</span></span>

- [<span data-ttu-id="f561c-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f561c-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
