---
title: ICorDebugChain::GetStackRange (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
ms.openlocfilehash: 64e697323377d664b7b1e36bbf5931a44465cc51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178957"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="62d34-102">ICorDebugChain::GetStackRange (Método)</span><span class="sxs-lookup"><span data-stu-id="62d34-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="62d34-103">Obtiene el intervalo de direcciones del segmento de pila para esta cadena.</span><span class="sxs-lookup"><span data-stu-id="62d34-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62d34-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62d34-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62d34-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62d34-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="62d34-106">[fuera] Puntero a `CORDB_ADDRESS` un valor que es la dirección inicial del segmento de pila.</span><span class="sxs-lookup"><span data-stu-id="62d34-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="62d34-107">[fuera] Puntero a `CORDB_ADDRESS` un valor que es la dirección final del segmento de pila.</span><span class="sxs-lookup"><span data-stu-id="62d34-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62d34-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="62d34-108">Remarks</span></span>  
 <span data-ttu-id="62d34-109">El rango numérico es significativo solo para la comparación de ubicaciones de marco de pila.</span><span class="sxs-lookup"><span data-stu-id="62d34-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="62d34-110">No puede hacer ninguna suposición sobre lo que realmente se almacena en la pila.</span><span class="sxs-lookup"><span data-stu-id="62d34-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62d34-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62d34-111">Requirements</span></span>  
 <span data-ttu-id="62d34-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62d34-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62d34-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62d34-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62d34-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62d34-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62d34-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62d34-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
