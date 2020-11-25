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
ms.openlocfilehash: 54ecce830b928ded115233eb99932cc15a471033
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703140"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="75b07-102">ICorDebugILFrame::GetLocalVariable (Método)</span><span class="sxs-lookup"><span data-stu-id="75b07-102">ICorDebugILFrame::GetLocalVariable Method</span></span>

<span data-ttu-id="75b07-103">Obtiene el valor de la variable local especificada en este marco de pila del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="75b07-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75b07-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75b07-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75b07-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75b07-105">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="75b07-106">de Índice de la variable local en este marco de pila de MSIL.</span><span class="sxs-lookup"><span data-stu-id="75b07-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="75b07-107">[out] Puntero a la dirección de un objeto ICorDebugValue que representa el valor recuperado.</span><span class="sxs-lookup"><span data-stu-id="75b07-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75b07-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="75b07-108">Remarks</span></span>  

 <span data-ttu-id="75b07-109">El `GetLocalVariable` método se puede utilizar en un marco de pila de MSIL o en un marco compilado Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="75b07-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75b07-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75b07-110">Requirements</span></span>  

 <span data-ttu-id="75b07-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75b07-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75b07-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75b07-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75b07-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75b07-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75b07-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75b07-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
