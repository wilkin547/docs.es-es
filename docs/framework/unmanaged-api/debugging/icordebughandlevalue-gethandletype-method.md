---
title: ICorDebugHandleValue::GetHandleType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.GetHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecc0b46618cd00ba4442e30c23a7b7e950382fee
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475598"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="9fafc-102">ICorDebugHandleValue::GetHandleType (Método)</span><span class="sxs-lookup"><span data-stu-id="9fafc-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="9fafc-103">Obtiene un valor que indica el tipo de identificador hace referencia este objeto ICorDebugHandleValue.</span><span class="sxs-lookup"><span data-stu-id="9fafc-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fafc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fafc-104">Syntax</span></span>  
  
```  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fafc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9fafc-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="9fafc-106">[out] Un puntero a un valor de la enumeración CorDebugHandleType que indica el tipo de este identificador.</span><span class="sxs-lookup"><span data-stu-id="9fafc-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fafc-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9fafc-107">Requirements</span></span>  
 <span data-ttu-id="9fafc-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fafc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fafc-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fafc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fafc-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fafc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fafc-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fafc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
