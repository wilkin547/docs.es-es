---
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
ms.openlocfilehash: 39175e338e4fd98dd4af1325138da732ed81c764
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137920"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="d8040-102">ICorDebugFrame::GetFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="d8040-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="d8040-103">Obtiene la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="d8040-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8040-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8040-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8040-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8040-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="d8040-106">enuncia Puntero a la dirección de un objeto ICorDebugFunction que representa la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="d8040-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8040-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8040-107">Remarks</span></span>  
 <span data-ttu-id="d8040-108">Puede producirse un error en el método `GetFunction` si el marco no está asociado a ninguna función determinada.</span><span class="sxs-lookup"><span data-stu-id="d8040-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8040-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8040-109">Requirements</span></span>  
 <span data-ttu-id="d8040-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8040-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8040-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8040-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8040-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8040-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8040-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8040-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
