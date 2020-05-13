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
ms.openlocfilehash: d6ce5a5cc64a5eb805faa5bb17a42a662940affe
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210259"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="48fc7-102">ICorDebugILFrame::GetLocalVariable (Método)</span><span class="sxs-lookup"><span data-stu-id="48fc7-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="48fc7-103">Obtiene el valor de la variable local especificada en este marco de pila del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="48fc7-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48fc7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48fc7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48fc7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48fc7-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="48fc7-106">de Índice de la variable local en este marco de pila de MSIL.</span><span class="sxs-lookup"><span data-stu-id="48fc7-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="48fc7-107">[out] Puntero a la dirección de un objeto ICorDebugValue que representa el valor recuperado.</span><span class="sxs-lookup"><span data-stu-id="48fc7-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48fc7-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="48fc7-108">Remarks</span></span>  
 <span data-ttu-id="48fc7-109">El `GetLocalVariable` método se puede utilizar en un marco de pila de MSIL o en un marco compilado Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="48fc7-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48fc7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48fc7-110">Requirements</span></span>  
 <span data-ttu-id="48fc7-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48fc7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48fc7-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48fc7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48fc7-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48fc7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48fc7-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48fc7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
