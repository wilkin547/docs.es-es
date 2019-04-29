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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c14b48a29993a65a0a0ab9fcb63bcb1e0d882042
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645375"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="bd1ad-102">ICorDebugChain::GetActiveFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="bd1ad-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="bd1ad-103">Obtiene el activo (es decir, más reciente) marco en la cadena.</span><span class="sxs-lookup"><span data-stu-id="bd1ad-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd1ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd1ad-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd1ad-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd1ad-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="bd1ad-106">[out] Un puntero a la dirección de un objeto ICorDebugFrame que representa el activo (es decir, más reciente) marco en la cadena.</span><span class="sxs-lookup"><span data-stu-id="bd1ad-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd1ad-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd1ad-107">Remarks</span></span>  
 <span data-ttu-id="bd1ad-108">Si está disponible, ningún marco de pila administrado `ppFrame` se establece en null.</span><span class="sxs-lookup"><span data-stu-id="bd1ad-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="bd1ad-109">Si el marco activo no está disponible, la llamada se realizará correctamente y `ppFrame` será null.</span><span class="sxs-lookup"><span data-stu-id="bd1ad-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="bd1ad-110">Marcos activa no estará disponibles para las cadenas iniciadas debido a CHAIN_ENTER_UNMANAGED y para algunas cadenas iniciadas debido a CHAIN_CLASS_INIT.</span><span class="sxs-lookup"><span data-stu-id="bd1ad-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="bd1ad-111">Consulte CorDebugChainReason (enumeración).</span><span class="sxs-lookup"><span data-stu-id="bd1ad-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd1ad-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd1ad-112">Requirements</span></span>  
 <span data-ttu-id="bd1ad-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd1ad-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd1ad-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd1ad-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd1ad-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd1ad-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd1ad-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd1ad-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
