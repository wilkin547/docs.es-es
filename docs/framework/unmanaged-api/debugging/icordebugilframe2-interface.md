---
title: ICorDebugILFrame2 Interfaz1
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccb39609b37aff09ac7890df562d6c08e3c3c159
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412440"
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="c0c46-102">ICorDebugILFrame2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="c0c46-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="c0c46-103">Una extensión lógica de ICorDebugILFrame (interfaz).</span><span class="sxs-lookup"><span data-stu-id="c0c46-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c0c46-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c0c46-104">Methods</span></span>  
  
|<span data-ttu-id="c0c46-105">Método</span><span class="sxs-lookup"><span data-stu-id="c0c46-105">Method</span></span>|<span data-ttu-id="c0c46-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0c46-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c0c46-107">EnumerateTypeParameters (método)</span><span class="sxs-lookup"><span data-stu-id="c0c46-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="c0c46-108">Obtiene un objeto ICorDebugTypeEnum que contiene el <xref:System.Type> parámetros de este marco.</span><span class="sxs-lookup"><span data-stu-id="c0c46-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="c0c46-109">RemapFunction (método)</span><span class="sxs-lookup"><span data-stu-id="c0c46-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="c0c46-110">Reasigna una función editada especificando el nuevo desplazamiento MSIL.</span><span class="sxs-lookup"><span data-stu-id="c0c46-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0c46-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0c46-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0c46-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c0c46-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0c46-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0c46-113">Requirements</span></span>  
 <span data-ttu-id="c0c46-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0c46-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0c46-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0c46-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0c46-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0c46-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0c46-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0c46-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0c46-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0c46-118">See Also</span></span>  
 [<span data-ttu-id="c0c46-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c0c46-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
