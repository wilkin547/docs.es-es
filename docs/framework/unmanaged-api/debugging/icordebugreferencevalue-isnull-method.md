---
title: ICorDebugReferenceValue::IsNull (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.IsNull
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type:
- apiref
ms.openlocfilehash: bcd4c8ba4b81821ae7dd9deaf0f76a76d335aff8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728399"
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="28187-102">ICorDebugReferenceValue::IsNull (Método)</span><span class="sxs-lookup"><span data-stu-id="28187-102">ICorDebugReferenceValue::IsNull Method</span></span>

<span data-ttu-id="28187-103">Obtiene un valor que indica si este ICorDebugReferenceValue es un valor null, en cuyo caso `ICorDebugReferenceValue` no señala a un objeto.</span><span class="sxs-lookup"><span data-stu-id="28187-103">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28187-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28187-104">Syntax</span></span>  
  
```cpp  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28187-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28187-105">Parameters</span></span>  

 `pbNull`  
 <span data-ttu-id="28187-106">enuncia Un puntero a un valor booleano que es `true` si este `ICorDebugReferenceValue` objeto es null; de lo contrario, `pbNull` es `false` .</span><span class="sxs-lookup"><span data-stu-id="28187-106">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28187-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28187-107">Requirements</span></span>  

 <span data-ttu-id="28187-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28187-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28187-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28187-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28187-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28187-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28187-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28187-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
