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
ms.openlocfilehash: daecd216b4d7e9c23336b8956c13735549be901b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730141"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="90832-102">ICorDebugChain::GetActiveFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="90832-102">ICorDebugChain::GetActiveFrame Method</span></span>

<span data-ttu-id="90832-103">Obtiene el marco activo (es decir, el más reciente) de la cadena.</span><span class="sxs-lookup"><span data-stu-id="90832-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90832-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90832-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90832-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="90832-105">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="90832-106">enuncia Puntero a la dirección de un objeto ICorDebugFrame que representa el marco activo (es decir, el más reciente) en la cadena.</span><span class="sxs-lookup"><span data-stu-id="90832-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90832-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="90832-107">Remarks</span></span>  

 <span data-ttu-id="90832-108">Si no hay ningún marco de pila administrado disponible, `ppFrame` se establece en NULL.</span><span class="sxs-lookup"><span data-stu-id="90832-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="90832-109">Si el marco activo no está disponible, la llamada se realizará correctamente y `ppFrame` será null.</span><span class="sxs-lookup"><span data-stu-id="90832-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="90832-110">Los marcos activos no estarán disponibles para las cadenas iniciadas debido a CHAIN_ENTER_UNMANAGED, y para algunas cadenas iniciadas debido a CHAIN_CLASS_INIT.</span><span class="sxs-lookup"><span data-stu-id="90832-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="90832-111">Vea la enumeración CorDebugChainReason (.</span><span class="sxs-lookup"><span data-stu-id="90832-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90832-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90832-112">Requirements</span></span>  

 <span data-ttu-id="90832-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90832-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90832-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90832-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90832-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90832-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90832-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90832-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
