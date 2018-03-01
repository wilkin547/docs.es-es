---
title: "ICorDebugFrame::GetStackRange (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c4c9c0a531d93ca2c7c72f50bcd2f7ee98887e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="42171-102">ICorDebugFrame::GetStackRange (Método)</span><span class="sxs-lookup"><span data-stu-id="42171-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="42171-103">Obtiene el intervalo de direcciones absolutas de este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="42171-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42171-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42171-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42171-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42171-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="42171-106">[out] Un puntero a un `CORDB_ADDRESS` que especifica la dirección inicial del marco de pila representado por este `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="42171-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="42171-107">[out] Un puntero a un `CORDB_ADDRESS` que especifica la dirección final del marco de pila representado por este `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="42171-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42171-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42171-108">Remarks</span></span>  
 <span data-ttu-id="42171-109">El intervalo de direcciones de la pila es útil para unir seguimientos de pila intercalados recopilados a partir de varios motores de depuración.</span><span class="sxs-lookup"><span data-stu-id="42171-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="42171-110">El intervalo numérico no proporciona información sobre el contenido del marco de pila.</span><span class="sxs-lookup"><span data-stu-id="42171-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="42171-111">Es significativo únicamente para la comparación de ubicaciones de marco de pila.</span><span class="sxs-lookup"><span data-stu-id="42171-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42171-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42171-112">Requirements</span></span>  
 <span data-ttu-id="42171-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42171-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42171-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42171-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42171-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42171-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42171-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42171-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
