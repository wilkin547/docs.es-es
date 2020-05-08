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
ms.openlocfilehash: 40ecc183c32500ad9e88ceb1bfc0528d717430e8
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894454"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="faf21-102">ICorDebugChain::GetStackRange (Método)</span><span class="sxs-lookup"><span data-stu-id="faf21-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="faf21-103">Obtiene el intervalo de direcciones del segmento de pila para esta cadena.</span><span class="sxs-lookup"><span data-stu-id="faf21-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faf21-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="faf21-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faf21-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="faf21-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="faf21-106">enuncia Un puntero a un `CORDB_ADDRESS` valor que es la dirección inicial del segmento de pila.</span><span class="sxs-lookup"><span data-stu-id="faf21-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="faf21-107">enuncia Un puntero a un `CORDB_ADDRESS` valor que es la dirección final del segmento de pila.</span><span class="sxs-lookup"><span data-stu-id="faf21-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faf21-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="faf21-108">Remarks</span></span>  
 <span data-ttu-id="faf21-109">El intervalo numérico solo es significativo para la comparación de las ubicaciones de los marcos de pila.</span><span class="sxs-lookup"><span data-stu-id="faf21-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="faf21-110">No puede hacer ninguna suposición sobre lo que realmente se almacena en la pila.</span><span class="sxs-lookup"><span data-stu-id="faf21-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faf21-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="faf21-111">Requirements</span></span>  
 <span data-ttu-id="faf21-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faf21-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faf21-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="faf21-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="faf21-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faf21-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faf21-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faf21-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
