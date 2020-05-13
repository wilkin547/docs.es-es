---
title: ICorDebugReferenceValue::Dereference (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
ms.openlocfilehash: 7c64823e1a5c519eb74b508af093afeb1132e608
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210090"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="3c3e9-102">ICorDebugReferenceValue::Dereference (Método)</span><span class="sxs-lookup"><span data-stu-id="3c3e9-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="3c3e9-103">Obtiene el objeto al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="3c3e9-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c3e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c3e9-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c3e9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c3e9-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="3c3e9-106">enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el objeto al que señala este objeto ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="3c3e9-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c3e9-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3c3e9-107">Remarks</span></span>  
 <span data-ttu-id="3c3e9-108">El `ICorDebugValue` objeto solo es válido mientras su referencia todavía no se ha deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="3c3e9-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c3e9-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c3e9-109">Requirements</span></span>  
 <span data-ttu-id="3c3e9-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c3e9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c3e9-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c3e9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c3e9-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c3e9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c3e9-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c3e9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
