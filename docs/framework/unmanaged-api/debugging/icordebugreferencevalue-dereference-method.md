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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2ea7ebff122622a0db46160d23574619664f8ad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745023"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="fc8e3-102">ICorDebugReferenceValue::Dereference (Método)</span><span class="sxs-lookup"><span data-stu-id="fc8e3-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="fc8e3-103">Obtiene el objeto que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="fc8e3-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc8e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc8e3-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc8e3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc8e3-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="fc8e3-106">[out] Un puntero a la dirección de ICorDebugValue que representa el objeto al que señala este objeto ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="fc8e3-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc8e3-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc8e3-107">Remarks</span></span>  
 <span data-ttu-id="fc8e3-108">La `ICorDebugValue` objeto es válido solo mientras aún no se ha deshabilitado su referencia.</span><span class="sxs-lookup"><span data-stu-id="fc8e3-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc8e3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc8e3-109">Requirements</span></span>  
 <span data-ttu-id="fc8e3-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc8e3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc8e3-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc8e3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc8e3-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc8e3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc8e3-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc8e3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
