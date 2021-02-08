---
description: 'Más información acerca de: interfaz ICorDebugILFrame2'
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
ms.openlocfilehash: 8379fda39a210e1df902dab3ac85132f04aee5fc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791314"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="16ede-103">Interfaz ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="16ede-103">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="16ede-104">Extensión lógica de la interfaz ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="16ede-104">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="16ede-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="16ede-105">Methods</span></span>  
  
|<span data-ttu-id="16ede-106">Método</span><span class="sxs-lookup"><span data-stu-id="16ede-106">Method</span></span>|<span data-ttu-id="16ede-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="16ede-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="16ede-108">Método EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="16ede-108">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="16ede-109">Obtiene un objeto ICorDebugTypeEnum que contiene los <xref:System.Type> parámetros de este marco.</span><span class="sxs-lookup"><span data-stu-id="16ede-109">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="16ede-110">Método RemapFunction</span><span class="sxs-lookup"><span data-stu-id="16ede-110">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="16ede-111">Vuelve a asignar una función editada especificando el nuevo desplazamiento de MSIL.</span><span class="sxs-lookup"><span data-stu-id="16ede-111">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16ede-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="16ede-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16ede-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="16ede-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16ede-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16ede-114">Requirements</span></span>  

 <span data-ttu-id="16ede-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16ede-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16ede-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16ede-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16ede-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16ede-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16ede-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16ede-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16ede-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="16ede-119">See also</span></span>

- [<span data-ttu-id="16ede-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="16ede-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
