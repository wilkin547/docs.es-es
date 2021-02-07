---
description: 'Más información acerca de: ICorDebugEnum:: Skip (método)'
title: ICorDebugEnum::Skip (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
ms.openlocfilehash: f72e400b3c2c911f609aca19f1b7d6a3a4e785cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694362"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="5bd68-103">ICorDebugEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="5bd68-103">ICorDebugEnum::Skip Method</span></span>

<span data-ttu-id="5bd68-104">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="5bd68-104">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bd68-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5bd68-105">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bd68-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5bd68-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="5bd68-107">de Número de elementos por los que se va a desplazar el cursor hacia delante.</span><span class="sxs-lookup"><span data-stu-id="5bd68-107">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bd68-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5bd68-108">Requirements</span></span>  

 <span data-ttu-id="5bd68-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bd68-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bd68-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5bd68-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bd68-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bd68-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bd68-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bd68-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd68-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bd68-113">See also</span></span>

- [<span data-ttu-id="5bd68-114">Interfaz ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="5bd68-114">ICorDebugEnum Interface</span></span>](icordebugenum-interface1.md)
