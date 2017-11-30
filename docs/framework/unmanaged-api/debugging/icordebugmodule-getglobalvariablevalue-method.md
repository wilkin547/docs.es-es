---
title: "ICorDebugModule::GetGlobalVariableValue (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetGlobalVariableValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetGlobalVariableValue
helpviewer_keywords:
- ICorDebugModule::GetGlobalVariableValue method [.NET Framework debugging]
- GetGlobalVariableValue method [.NET Framework debugging]
ms.assetid: bbc0881c-6a59-41a0-b5ee-2f3d1b71684c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 00fb56353652e2fdeac7d7b42c030d9105cc9aca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="e5739-102">ICorDebugModule::GetGlobalVariableValue (Método)</span><span class="sxs-lookup"><span data-stu-id="e5739-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="e5739-103">Obtiene el valor de la variable global especificada.</span><span class="sxs-lookup"><span data-stu-id="e5739-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5739-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5739-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5739-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5739-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="e5739-106">[in] Un `mdFieldDef` símbolo (token) que hace referencia a los metadatos que describen la variable global.</span><span class="sxs-lookup"><span data-stu-id="e5739-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e5739-107">[out] Un puntero a la dirección de un objeto ICorDebugValue que representa el valor de la variable global especificada.</span><span class="sxs-lookup"><span data-stu-id="e5739-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5739-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5739-108">Requirements</span></span>  
 <span data-ttu-id="e5739-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5739-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5739-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5739-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5739-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5739-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5739-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5739-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
