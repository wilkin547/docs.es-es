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
ms.openlocfilehash: 6eb76ddd6ee8b2a00aac3af9ebf815338d29f194
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212171"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="0dcda-102">ICorDebugHandleValue::GetHandleType (Método)</span><span class="sxs-lookup"><span data-stu-id="0dcda-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="0dcda-103">Obtiene un valor que indica el tipo de identificador al que hace referencia este objeto ICorDebugHandleValue.</span><span class="sxs-lookup"><span data-stu-id="0dcda-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dcda-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0dcda-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dcda-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0dcda-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="0dcda-106">enuncia Un puntero a un valor de la enumeración CorDebugHandleType (que indica el tipo de este identificador.</span><span class="sxs-lookup"><span data-stu-id="0dcda-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dcda-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0dcda-107">Requirements</span></span>  
 <span data-ttu-id="0dcda-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dcda-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dcda-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0dcda-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0dcda-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dcda-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dcda-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dcda-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
