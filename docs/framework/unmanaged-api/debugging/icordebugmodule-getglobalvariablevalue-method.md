---
title: ICorDebugModule::GetGlobalVariableValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetGlobalVariableValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetGlobalVariableValue
helpviewer_keywords:
- ICorDebugModule::GetGlobalVariableValue method [.NET Framework debugging]
- GetGlobalVariableValue method [.NET Framework debugging]
ms.assetid: bbc0881c-6a59-41a0-b5ee-2f3d1b71684c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd79299dcfdb03b703c2cab214ba448631daa6f2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763483"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="b49dd-102">ICorDebugModule::GetGlobalVariableValue (Método)</span><span class="sxs-lookup"><span data-stu-id="b49dd-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="b49dd-103">Obtiene el valor de la variable global especificada.</span><span class="sxs-lookup"><span data-stu-id="b49dd-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b49dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b49dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b49dd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b49dd-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="b49dd-106">[in] Un `mdFieldDef` símbolo (token) que hace referencia a los metadatos que describen la variable global.</span><span class="sxs-lookup"><span data-stu-id="b49dd-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b49dd-107">[out] Un puntero a la dirección de un objeto ICorDebugValue que representa el valor de la variable global especificada.</span><span class="sxs-lookup"><span data-stu-id="b49dd-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b49dd-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b49dd-108">Requirements</span></span>  
 <span data-ttu-id="b49dd-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b49dd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b49dd-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b49dd-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b49dd-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b49dd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b49dd-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b49dd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
