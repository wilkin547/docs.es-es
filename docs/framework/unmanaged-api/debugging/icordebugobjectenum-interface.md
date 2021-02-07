---
description: 'Más información acerca de: interfaz ICorDebugObjectEnum ('
title: Interfaz ICorDebugObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
ms.openlocfilehash: d5cd8580bfa81af7d644c2fb11524a43a9062ddf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722248"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="2ff76-103">Interfaz ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="2ff76-103">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="2ff76-104">Implementa los métodos ICorDebugEnum y enumera las matrices de objetos por sus direcciones virtuales relativas (RVA).</span><span class="sxs-lookup"><span data-stu-id="2ff76-104">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ff76-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2ff76-105">Methods</span></span>  
  
|<span data-ttu-id="2ff76-106">Método</span><span class="sxs-lookup"><span data-stu-id="2ff76-106">Method</span></span>|<span data-ttu-id="2ff76-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ff76-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ff76-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="2ff76-108">Next Method</span></span>](icordebugobjectenum-next-method.md)|<span data-ttu-id="2ff76-109">Obtiene las RVA del número especificado de objetos de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="2ff76-109">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ff76-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2ff76-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ff76-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="2ff76-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ff76-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ff76-112">Requirements</span></span>  

 <span data-ttu-id="2ff76-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ff76-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ff76-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ff76-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ff76-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ff76-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ff76-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ff76-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ff76-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ff76-117">See also</span></span>

- [<span data-ttu-id="2ff76-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2ff76-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
