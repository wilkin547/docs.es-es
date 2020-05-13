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
ms.openlocfilehash: 2e0f284625e99215900c6aaab94e4eae611787ed
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212105"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="5b016-102">Interfaz ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="5b016-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="5b016-103">Extensión lógica de la interfaz ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="5b016-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b016-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5b016-104">Methods</span></span>  
  
|<span data-ttu-id="5b016-105">Método</span><span class="sxs-lookup"><span data-stu-id="5b016-105">Method</span></span>|<span data-ttu-id="5b016-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b016-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b016-107">Método EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="5b016-107">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="5b016-108">Obtiene un objeto ICorDebugTypeEnum que contiene los <xref:System.Type> parámetros de este marco.</span><span class="sxs-lookup"><span data-stu-id="5b016-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="5b016-109">Método RemapFunction</span><span class="sxs-lookup"><span data-stu-id="5b016-109">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="5b016-110">Vuelve a asignar una función editada especificando el nuevo desplazamiento de MSIL.</span><span class="sxs-lookup"><span data-stu-id="5b016-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b016-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5b016-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5b016-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5b016-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b016-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b016-113">Requirements</span></span>  
 <span data-ttu-id="5b016-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b016-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b016-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b016-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b016-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b016-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b016-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b016-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b016-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b016-118">See also</span></span>

- [<span data-ttu-id="5b016-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5b016-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
