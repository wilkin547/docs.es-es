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
ms.openlocfilehash: 7e32f3f4f6613d34e2b40946ed3eadb8eb0a7c1f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212576"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="9da70-102">ICorDebugModule::GetGlobalVariableValue (Método)</span><span class="sxs-lookup"><span data-stu-id="9da70-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="9da70-103">Obtiene el valor de la variable global especificada.</span><span class="sxs-lookup"><span data-stu-id="9da70-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9da70-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9da70-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9da70-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9da70-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="9da70-106">de `mdFieldDef`Token que hace referencia a los metadatos que describen la variable global.</span><span class="sxs-lookup"><span data-stu-id="9da70-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="9da70-107">enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el valor de la variable global especificada.</span><span class="sxs-lookup"><span data-stu-id="9da70-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9da70-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9da70-108">Requirements</span></span>  
 <span data-ttu-id="9da70-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9da70-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9da70-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9da70-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9da70-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9da70-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9da70-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9da70-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
