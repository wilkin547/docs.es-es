---
title: Interfaz ICorDebugILFrame2
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
ms.openlocfilehash: 3ada9e19bb1a92b3bd7e41340b99bf81b651dd37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725019"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="0f484-102">Interfaz ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="0f484-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="0f484-103">Extensión lógica de la interfaz ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="0f484-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0f484-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0f484-104">Methods</span></span>  
  
|<span data-ttu-id="0f484-105">Método</span><span class="sxs-lookup"><span data-stu-id="0f484-105">Method</span></span>|<span data-ttu-id="0f484-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f484-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0f484-107">Método EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="0f484-107">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="0f484-108">Obtiene un objeto ICorDebugTypeEnum que contiene los <xref:System.Type> parámetros de este marco.</span><span class="sxs-lookup"><span data-stu-id="0f484-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="0f484-109">Método RemapFunction</span><span class="sxs-lookup"><span data-stu-id="0f484-109">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="0f484-110">Vuelve a asignar una función editada especificando el nuevo desplazamiento de MSIL.</span><span class="sxs-lookup"><span data-stu-id="0f484-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f484-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0f484-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f484-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="0f484-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f484-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f484-113">Requirements</span></span>  

 <span data-ttu-id="0f484-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f484-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f484-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f484-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f484-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f484-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f484-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f484-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f484-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0f484-118">See also</span></span>

- [<span data-ttu-id="0f484-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="0f484-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
