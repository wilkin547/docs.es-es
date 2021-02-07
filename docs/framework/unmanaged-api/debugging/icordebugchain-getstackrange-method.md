---
description: 'Más información sobre: ICorDebugChain:: GetStackRange ((método)'
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
ms.openlocfilehash: 066dda06564655350d799dabb54acd622b828172
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694936"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="a554e-103">ICorDebugChain::GetStackRange (Método)</span><span class="sxs-lookup"><span data-stu-id="a554e-103">ICorDebugChain::GetStackRange Method</span></span>

<span data-ttu-id="a554e-104">Obtiene el intervalo de direcciones del segmento de pila para esta cadena.</span><span class="sxs-lookup"><span data-stu-id="a554e-104">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a554e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a554e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a554e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a554e-106">Parameters</span></span>  

 `pStart`  
 <span data-ttu-id="a554e-107">enuncia Un puntero a un `CORDB_ADDRESS` valor que es la dirección inicial del segmento de pila.</span><span class="sxs-lookup"><span data-stu-id="a554e-107">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="a554e-108">enuncia Un puntero a un `CORDB_ADDRESS` valor que es la dirección final del segmento de pila.</span><span class="sxs-lookup"><span data-stu-id="a554e-108">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a554e-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a554e-109">Remarks</span></span>  

 <span data-ttu-id="a554e-110">El intervalo numérico solo es significativo para la comparación de las ubicaciones de los marcos de pila.</span><span class="sxs-lookup"><span data-stu-id="a554e-110">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="a554e-111">No puede hacer ninguna suposición sobre lo que realmente se almacena en la pila.</span><span class="sxs-lookup"><span data-stu-id="a554e-111">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a554e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a554e-112">Requirements</span></span>  

 <span data-ttu-id="a554e-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a554e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a554e-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a554e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a554e-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a554e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a554e-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a554e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
