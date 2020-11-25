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
ms.openlocfilehash: 821eae8ea5b4147408e9fe60d1e5b70c7936959e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696250"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="5a4d7-102">Interfaz ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="5a4d7-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="5a4d7-103">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a4d7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5a4d7-104">Methods</span></span>  
  
|<span data-ttu-id="5a4d7-105">Método</span><span class="sxs-lookup"><span data-stu-id="5a4d7-105">Method</span></span>|<span data-ttu-id="5a4d7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a4d7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a4d7-107">Método EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="5a4d7-107">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="5a4d7-108">Obtiene un enumerador para los módulos incluidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="5a4d7-109">Método GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="5a4d7-109">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="5a4d7-110">Obtiene un puntero de interfaz al dominio de aplicación que contiene esta `ICorDebugAssembly` instancia.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="5a4d7-111">Método GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="5a4d7-111">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="5a4d7-112">No se implementa en la versión actual del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="5a4d7-113">GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="5a4d7-113">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="5a4d7-114">Obtiene el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="5a4d7-115">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="5a4d7-115">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="5a4d7-116">Obtiene la instancia de ICorDebugProcess en la que se ejecuta el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a4d7-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a4d7-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a4d7-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a4d7-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a4d7-119">Requirements</span></span>  

 <span data-ttu-id="5a4d7-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a4d7-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a4d7-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a4d7-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a4d7-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a4d7-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a4d7-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a4d7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a4d7-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a4d7-124">See also</span></span>

- [<span data-ttu-id="5a4d7-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5a4d7-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
