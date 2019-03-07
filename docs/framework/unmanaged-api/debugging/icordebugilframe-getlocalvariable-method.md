---
title: ICorDebugILFrame::GetLocalVariable (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ebd36f01297f24c050f84fb67e7673f8641fe206
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475247"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="6dfb0-102">ICorDebugILFrame::GetLocalVariable (Método)</span><span class="sxs-lookup"><span data-stu-id="6dfb0-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="6dfb0-103">Obtiene el valor de la variable local especificada en este marco de pila del lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6dfb0-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dfb0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6dfb0-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6dfb0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6dfb0-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="6dfb0-106">[in] El índice de la variable local en este marco de pila MSIL.</span><span class="sxs-lookup"><span data-stu-id="6dfb0-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="6dfb0-107">[out] Un puntero a la dirección de un objeto ICorDebugValue que representa el valor recuperado.</span><span class="sxs-lookup"><span data-stu-id="6dfb0-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6dfb0-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6dfb0-108">Remarks</span></span>  
 <span data-ttu-id="6dfb0-109">El `GetLocalVariable` método puede utilizarse en un marco de pila MSIL o en un marco compilado just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="6dfb0-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dfb0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6dfb0-110">Requirements</span></span>  
 <span data-ttu-id="6dfb0-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dfb0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dfb0-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6dfb0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6dfb0-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6dfb0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6dfb0-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dfb0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
