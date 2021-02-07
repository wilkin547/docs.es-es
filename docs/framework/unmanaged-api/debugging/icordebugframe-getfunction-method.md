---
description: 'Más información sobre: ICorDebugFrame:: GetFunction ((método)'
title: ICorDebugFrame::GetFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
ms.openlocfilehash: 0309a066f686e55d086de1cbb040eea58e031df3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692997"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="bb08e-103">ICorDebugFrame::GetFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="bb08e-103">ICorDebugFrame::GetFunction Method</span></span>

<span data-ttu-id="bb08e-104">Obtiene la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="bb08e-104">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb08e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb08e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb08e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bb08e-106">Parameters</span></span>  

 `ppFunction`  
 <span data-ttu-id="bb08e-107">enuncia Puntero a la dirección de un objeto ICorDebugFunction que representa la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="bb08e-107">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb08e-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bb08e-108">Remarks</span></span>  

 <span data-ttu-id="bb08e-109">El `GetFunction` método puede producir un error si el marco no está asociado a ninguna función determinada.</span><span class="sxs-lookup"><span data-stu-id="bb08e-109">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb08e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb08e-110">Requirements</span></span>  

 <span data-ttu-id="bb08e-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb08e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb08e-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb08e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb08e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb08e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb08e-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb08e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
