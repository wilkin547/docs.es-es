---
description: 'Más información sobre: interfaz ICorDebugAssembly'
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
ms.openlocfilehash: 746b5f4b2f26550788708d93bf0dd50f5f495041
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711952"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="d5900-103">Interfaz ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="d5900-103">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="d5900-104">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d5900-104">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5900-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d5900-105">Methods</span></span>  
  
|<span data-ttu-id="d5900-106">Método</span><span class="sxs-lookup"><span data-stu-id="d5900-106">Method</span></span>|<span data-ttu-id="d5900-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5900-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5900-108">Método EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="d5900-108">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="d5900-109">Obtiene un enumerador para los módulos incluidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d5900-109">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="d5900-110">Método GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="d5900-110">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="d5900-111">Obtiene un puntero de interfaz al dominio de aplicación que contiene esta `ICorDebugAssembly` instancia.</span><span class="sxs-lookup"><span data-stu-id="d5900-111">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="d5900-112">Método GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="d5900-112">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="d5900-113">No se implementa en la versión actual del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d5900-113">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="d5900-114">Método GetName</span><span class="sxs-lookup"><span data-stu-id="d5900-114">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="d5900-115">Obtiene el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d5900-115">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="d5900-116">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="d5900-116">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="d5900-117">Obtiene la instancia de ICorDebugProcess en la que se ejecuta el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d5900-117">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5900-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d5900-118">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d5900-119">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="d5900-119">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5900-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5900-120">Requirements</span></span>  

 <span data-ttu-id="d5900-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5900-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5900-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5900-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5900-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5900-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5900-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5900-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5900-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5900-125">See also</span></span>

- [<span data-ttu-id="d5900-126">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d5900-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
