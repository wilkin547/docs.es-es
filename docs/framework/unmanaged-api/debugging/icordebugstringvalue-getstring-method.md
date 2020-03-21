---
title: ICorDebugStringValue::GetString (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type:
- apiref
ms.openlocfilehash: e23133176cbd703a58c92f9bf1ead530b0bbb8a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178501"
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="5ddea-102">ICorDebugStringValue::GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="5ddea-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="5ddea-103">Obtiene la cadena a la que hace referencia este ICorDebugStringValue.</span><span class="sxs-lookup"><span data-stu-id="5ddea-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ddea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ddea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]
        WCHAR       szString[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ddea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5ddea-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="5ddea-106">[in] Tamaño de la matriz `szString`.</span><span class="sxs-lookup"><span data-stu-id="5ddea-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="5ddea-107">[fuera] Puntero al número de caracteres `szString` devueltos en la matriz.</span><span class="sxs-lookup"><span data-stu-id="5ddea-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="5ddea-108">[fuera] Matriz que almacena la cadena recuperada.</span><span class="sxs-lookup"><span data-stu-id="5ddea-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ddea-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ddea-109">Requirements</span></span>  
 <span data-ttu-id="5ddea-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ddea-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ddea-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ddea-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ddea-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ddea-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ddea-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ddea-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
