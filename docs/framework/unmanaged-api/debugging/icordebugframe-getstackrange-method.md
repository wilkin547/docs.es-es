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
ms.openlocfilehash: 5da87071bc23ac17a3077049cd77f0fb8611439f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413025"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="26deb-102">ICorDebugFrame::GetStackRange (Método)</span><span class="sxs-lookup"><span data-stu-id="26deb-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="26deb-103">Obtiene el intervalo de direcciones absolutas de este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="26deb-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26deb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26deb-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26deb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="26deb-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="26deb-106">[out] Un puntero a un `CORDB_ADDRESS` que especifica la dirección inicial del marco de pila representado por este `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="26deb-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="26deb-107">[out] Un puntero a un `CORDB_ADDRESS` que especifica la dirección final del marco de pila representado por este `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="26deb-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26deb-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26deb-108">Remarks</span></span>  
 <span data-ttu-id="26deb-109">El intervalo de direcciones de la pila es útil para unir seguimientos de pila intercalados recopilados a partir de varios motores de depuración.</span><span class="sxs-lookup"><span data-stu-id="26deb-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="26deb-110">El intervalo numérico no proporciona información sobre el contenido del marco de pila.</span><span class="sxs-lookup"><span data-stu-id="26deb-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="26deb-111">Es significativo únicamente para la comparación de ubicaciones de marco de pila.</span><span class="sxs-lookup"><span data-stu-id="26deb-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26deb-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26deb-112">Requirements</span></span>  
 <span data-ttu-id="26deb-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26deb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26deb-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26deb-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26deb-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26deb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26deb-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26deb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
