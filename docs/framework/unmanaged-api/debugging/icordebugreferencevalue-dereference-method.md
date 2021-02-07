---
description: 'Más información acerca de: ICorDebugReferenceValue::D método ereference'
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
ms.openlocfilehash: af225f746a9c67a90a7ad73046cd03401e4ba735
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691112"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="45df7-103">ICorDebugReferenceValue::Dereference (Método)</span><span class="sxs-lookup"><span data-stu-id="45df7-103">ICorDebugReferenceValue::Dereference Method</span></span>

<span data-ttu-id="45df7-104">Obtiene el objeto al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="45df7-104">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45df7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45df7-105">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45df7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45df7-106">Parameters</span></span>  

 `ppValue`  
 <span data-ttu-id="45df7-107">enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el objeto al que señala este objeto ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="45df7-107">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45df7-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="45df7-108">Remarks</span></span>  

 <span data-ttu-id="45df7-109">El `ICorDebugValue` objeto solo es válido mientras su referencia todavía no se ha deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="45df7-109">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45df7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45df7-110">Requirements</span></span>  

 <span data-ttu-id="45df7-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45df7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45df7-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45df7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45df7-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45df7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45df7-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45df7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
