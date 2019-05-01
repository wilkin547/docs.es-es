---
title: ICorDebugFrame::GetStackRange (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 43532888d181adcb7a7e3760f2a5e3d8f664a35c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995818"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="f35bf-102">ICorDebugFrame::GetStackRange (Método)</span><span class="sxs-lookup"><span data-stu-id="f35bf-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="f35bf-103">Obtiene el intervalo de direcciones absolutas de este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="f35bf-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f35bf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f35bf-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f35bf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f35bf-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="f35bf-106">[out] Un puntero a un `CORDB_ADDRESS` que especifica la dirección inicial del marco de pila representado por este `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="f35bf-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="f35bf-107">[out] Un puntero a un `CORDB_ADDRESS` que especifica la dirección final del marco de pila representado por este `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="f35bf-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f35bf-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f35bf-108">Remarks</span></span>  
 <span data-ttu-id="f35bf-109">El intervalo de direcciones de la pila es útil para juntar los seguimientos de pila intercalados recopilados de varios motores de depuración.</span><span class="sxs-lookup"><span data-stu-id="f35bf-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="f35bf-110">El intervalo numérico no proporciona información sobre el contenido del marco de pila.</span><span class="sxs-lookup"><span data-stu-id="f35bf-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="f35bf-111">Es significativo únicamente para la comparación de las ubicaciones del marco de pila.</span><span class="sxs-lookup"><span data-stu-id="f35bf-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f35bf-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f35bf-112">Requirements</span></span>  
 <span data-ttu-id="f35bf-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f35bf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f35bf-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f35bf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f35bf-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f35bf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f35bf-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f35bf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
