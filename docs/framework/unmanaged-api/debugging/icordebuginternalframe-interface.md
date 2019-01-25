---
title: ICorDebugInternalFrame (Interfaz1)
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1fab8221bd160a74bb44c3ed0721ad4620e93419
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692800"
---
# <a name="icordebuginternalframe-interface1"></a><span data-ttu-id="2860b-102">ICorDebugInternalFrame (Interfaz1)</span><span class="sxs-lookup"><span data-stu-id="2860b-102">ICorDebugInternalFrame Interface1</span></span>
<span data-ttu-id="2860b-103">Representa un marco en la pila interna del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2860b-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="2860b-104">Esta interfaz es una subclase de ICorDebugFrame (interfaz).</span><span class="sxs-lookup"><span data-stu-id="2860b-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2860b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2860b-105">Methods</span></span>  
  
|<span data-ttu-id="2860b-106">Método</span><span class="sxs-lookup"><span data-stu-id="2860b-106">Method</span></span>|<span data-ttu-id="2860b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2860b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2860b-108">GetFrameType (método)</span><span class="sxs-lookup"><span data-stu-id="2860b-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="2860b-109">Obtiene el tipo de este marco interno.</span><span class="sxs-lookup"><span data-stu-id="2860b-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2860b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2860b-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2860b-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="2860b-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2860b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2860b-112">Requirements</span></span>  
 <span data-ttu-id="2860b-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2860b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2860b-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2860b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2860b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2860b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2860b-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2860b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2860b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2860b-117">See also</span></span>
- [<span data-ttu-id="2860b-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2860b-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
