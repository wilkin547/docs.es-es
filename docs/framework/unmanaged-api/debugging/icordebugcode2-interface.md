---
description: 'Más información acerca de: interfaz ICorDebugCode2'
title: Interfaz ICorDebugCode2
ms.date: 03/30/2017
api_name:
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
ms.openlocfilehash: 29fd657ec56993d47ee57aa41c81b45e75352697
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765053"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="17855-103">Interfaz ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="17855-103">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="17855-104">Proporciona métodos que amplían las capacidades de "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="17855-104">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="17855-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="17855-105">Methods</span></span>  
  
|<span data-ttu-id="17855-106">Método</span><span class="sxs-lookup"><span data-stu-id="17855-106">Method</span></span>|<span data-ttu-id="17855-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="17855-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="17855-108">Método GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="17855-108">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="17855-109">Obtiene los fragmentos de código de los que está compuesto este objeto de código.</span><span class="sxs-lookup"><span data-stu-id="17855-109">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="17855-110">Método GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="17855-110">GetCompilerFlags Method</span></span>](icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="17855-111">Obtiene las marcas que especifican las condiciones bajo las que este objeto de código se compiló Just-In-Time (JIT) o se generó usando el generador de imágenes nativas (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="17855-111">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17855-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="17855-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17855-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="17855-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17855-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17855-114">Requirements</span></span>  

 <span data-ttu-id="17855-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17855-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17855-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17855-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17855-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17855-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17855-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17855-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17855-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="17855-119">See also</span></span>

- [<span data-ttu-id="17855-120">ICorDebugCode3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="17855-120">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="17855-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="17855-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
