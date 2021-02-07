---
description: 'Más información acerca de: ICorDebugCode:: GetFunction ((método)'
title: ICorDebugCode::GetFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
ms.openlocfilehash: c90635bf1821d70d6d056d5cbd495ddfa2d2a2ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711211"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="ec58b-103">ICorDebugCode::GetFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="ec58b-103">ICorDebugCode::GetFunction Method</span></span>

<span data-ttu-id="ec58b-104">Obtiene el "ICorDebugFunction" asociado a este "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="ec58b-104">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec58b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec58b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec58b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec58b-106">Parameters</span></span>  

 `ppFunction`  
 <span data-ttu-id="ec58b-107">enuncia Puntero a la dirección de la función.</span><span class="sxs-lookup"><span data-stu-id="ec58b-107">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec58b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ec58b-108">Remarks</span></span>  

 <span data-ttu-id="ec58b-109">`ICorDebugCode` y `ICorDebugFunction` mantienen una relación uno a uno.</span><span class="sxs-lookup"><span data-stu-id="ec58b-109">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec58b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec58b-110">Requirements</span></span>  

 <span data-ttu-id="ec58b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec58b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec58b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec58b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec58b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec58b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec58b-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec58b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
