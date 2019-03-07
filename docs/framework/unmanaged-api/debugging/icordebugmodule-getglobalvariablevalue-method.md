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
ms.openlocfilehash: 00e747e43f67533771665313f4d420e4725945cd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485361"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="2633a-102">ICorDebugModule::GetGlobalVariableValue (Método)</span><span class="sxs-lookup"><span data-stu-id="2633a-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="2633a-103">Obtiene el valor de la variable global especificada.</span><span class="sxs-lookup"><span data-stu-id="2633a-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2633a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2633a-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2633a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2633a-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="2633a-106">[in] Un `mdFieldDef` símbolo (token) que hace referencia a los metadatos que describen la variable global.</span><span class="sxs-lookup"><span data-stu-id="2633a-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="2633a-107">[out] Un puntero a la dirección de un objeto ICorDebugValue que representa el valor de la variable global especificada.</span><span class="sxs-lookup"><span data-stu-id="2633a-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2633a-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2633a-108">Requirements</span></span>  
 <span data-ttu-id="2633a-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2633a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2633a-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2633a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2633a-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2633a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2633a-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2633a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
