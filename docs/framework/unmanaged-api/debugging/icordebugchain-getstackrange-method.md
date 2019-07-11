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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a6db1990df2ed6b29d548c147ed40b5bc98254d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745690"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="f1d74-102">ICorDebugChain::GetStackRange (Método)</span><span class="sxs-lookup"><span data-stu-id="f1d74-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="f1d74-103">Obtiene el intervalo de direcciones del segmento de pila para esta cadena.</span><span class="sxs-lookup"><span data-stu-id="f1d74-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1d74-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1d74-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1d74-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1d74-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="f1d74-106">[out] Un puntero a un `CORDB_ADDRESS` valor que es la dirección inicial del segmento de pila.</span><span class="sxs-lookup"><span data-stu-id="f1d74-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="f1d74-107">[out] Un puntero a un `CORDB_ADDRESS` valor que es la dirección final del segmento de pila.</span><span class="sxs-lookup"><span data-stu-id="f1d74-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1d74-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1d74-108">Remarks</span></span>  
 <span data-ttu-id="f1d74-109">El intervalo numérico es significativo únicamente para la comparación de las ubicaciones del marco de pila.</span><span class="sxs-lookup"><span data-stu-id="f1d74-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="f1d74-110">No se puede hacer ninguna suposición sobre lo que realmente se almacena en la pila.</span><span class="sxs-lookup"><span data-stu-id="f1d74-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1d74-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1d74-111">Requirements</span></span>  
 <span data-ttu-id="f1d74-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1d74-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1d74-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1d74-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1d74-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1d74-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1d74-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1d74-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
