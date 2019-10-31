---
title: ICorDebugChain::GetActiveFrame (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
ms.openlocfilehash: 03cb1556ee971124ed4c591f38d9f892fc7df7b0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192155"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="857c9-102">ICorDebugChain::GetActiveFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="857c9-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="857c9-103">Obtiene el marco activo (es decir, el más reciente) de la cadena.</span><span class="sxs-lookup"><span data-stu-id="857c9-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="857c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="857c9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="857c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="857c9-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="857c9-106">enuncia Puntero a la dirección de un objeto ICorDebugFrame que representa el marco activo (es decir, el más reciente) en la cadena.</span><span class="sxs-lookup"><span data-stu-id="857c9-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="857c9-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="857c9-107">Remarks</span></span>  
 <span data-ttu-id="857c9-108">Si no hay ningún marco de pila administrado disponible, `ppFrame` se establece en NULL.</span><span class="sxs-lookup"><span data-stu-id="857c9-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="857c9-109">Si el marco activo no está disponible, la llamada se realizará correctamente y `ppFrame` será null.</span><span class="sxs-lookup"><span data-stu-id="857c9-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="857c9-110">Los marcos activos no estarán disponibles para las cadenas iniciadas debido a CHAIN_ENTER_UNMANAGED y, para algunas cadenas iniciadas debido a CHAIN_CLASS_INIT.</span><span class="sxs-lookup"><span data-stu-id="857c9-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="857c9-111">Vea la enumeración CorDebugChainReason (.</span><span class="sxs-lookup"><span data-stu-id="857c9-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="857c9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="857c9-112">Requirements</span></span>  
 <span data-ttu-id="857c9-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="857c9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="857c9-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="857c9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="857c9-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="857c9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="857c9-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="857c9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
