---
description: 'Más información sobre: ICorDebugChain:: GetActiveFrame ((método)'
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
ms.openlocfilehash: d46906d9d6c671880d9446d889cdf9f83f3b4366
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661429"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="ecac3-103">ICorDebugChain::GetActiveFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="ecac3-103">ICorDebugChain::GetActiveFrame Method</span></span>

<span data-ttu-id="ecac3-104">Obtiene el marco activo (es decir, el más reciente) de la cadena.</span><span class="sxs-lookup"><span data-stu-id="ecac3-104">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecac3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecac3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecac3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ecac3-106">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="ecac3-107">enuncia Puntero a la dirección de un objeto ICorDebugFrame que representa el marco activo (es decir, el más reciente) en la cadena.</span><span class="sxs-lookup"><span data-stu-id="ecac3-107">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecac3-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ecac3-108">Remarks</span></span>  

 <span data-ttu-id="ecac3-109">Si no hay ningún marco de pila administrado disponible, `ppFrame` se establece en NULL.</span><span class="sxs-lookup"><span data-stu-id="ecac3-109">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="ecac3-110">Si el marco activo no está disponible, la llamada se realizará correctamente y `ppFrame` será null.</span><span class="sxs-lookup"><span data-stu-id="ecac3-110">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="ecac3-111">Los marcos activos no estarán disponibles para las cadenas iniciadas debido a CHAIN_ENTER_UNMANAGED, y para algunas cadenas iniciadas debido a CHAIN_CLASS_INIT.</span><span class="sxs-lookup"><span data-stu-id="ecac3-111">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="ecac3-112">Vea la enumeración CorDebugChainReason (.</span><span class="sxs-lookup"><span data-stu-id="ecac3-112">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecac3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ecac3-113">Requirements</span></span>  

 <span data-ttu-id="ecac3-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecac3-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecac3-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecac3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecac3-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecac3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecac3-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecac3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
