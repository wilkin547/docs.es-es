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
ms.openlocfilehash: cbcee923ecbb1106bb129f05d2e602a0fd17258d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732494"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="f033e-102">ICorDebugReferenceValue::Dereference (Método)</span><span class="sxs-lookup"><span data-stu-id="f033e-102">ICorDebugReferenceValue::Dereference Method</span></span>

<span data-ttu-id="f033e-103">Obtiene el objeto al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="f033e-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f033e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f033e-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f033e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f033e-105">Parameters</span></span>  

 `ppValue`  
 <span data-ttu-id="f033e-106">enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el objeto al que señala este objeto ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="f033e-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f033e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f033e-107">Remarks</span></span>  

 <span data-ttu-id="f033e-108">El `ICorDebugValue` objeto solo es válido mientras su referencia todavía no se ha deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f033e-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f033e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f033e-109">Requirements</span></span>  

 <span data-ttu-id="f033e-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f033e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f033e-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f033e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f033e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f033e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f033e-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f033e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
