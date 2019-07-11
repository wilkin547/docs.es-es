---
title: ICorDebugArrayValue::GetElementType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementType
helpviewer_keywords:
- ICorDebugArrayValue::GetElementType method [.NET Framework debugging]
- GetElementType method [.NET Framework debugging]
ms.assetid: ed71961e-ae9b-4dfc-9554-06637696d697
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e0159ce6ad1087838681214533d386f4d44cee2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737476"
---
# <a name="icordebugarrayvaluegetelementtype-method"></a><span data-ttu-id="94263-102">ICorDebugArrayValue::GetElementType (Método)</span><span class="sxs-lookup"><span data-stu-id="94263-102">ICorDebugArrayValue::GetElementType Method</span></span>
<span data-ttu-id="94263-103">Obtiene un valor que indica el tipo simple de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="94263-103">Gets a value that indicates the simple type of the elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94263-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94263-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementType (  
    [out] CorElementType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94263-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="94263-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="94263-106">[out] Un puntero a un valor de la enumeración CorElementType que indica el tipo.</span><span class="sxs-lookup"><span data-stu-id="94263-106">[out] A pointer to a value of the CorElementType enumeration that indicates the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94263-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94263-107">Requirements</span></span>  
 <span data-ttu-id="94263-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94263-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94263-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94263-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94263-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94263-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94263-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94263-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
