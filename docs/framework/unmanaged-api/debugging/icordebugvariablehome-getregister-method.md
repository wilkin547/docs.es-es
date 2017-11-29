---
title: "ICorDebugVariableHome::GetRegister (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetRegister
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f16e4bfe4767e1b49d7dacf0481e8911a90e178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="59668-102">ICorDebugVariableHome::GetRegister (método)</span><span class="sxs-lookup"><span data-stu-id="59668-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="59668-103">Obtiene el registro que contiene una variable con un tipo de ubicación de `VLT_REGISTER`y el registro de base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="59668-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59668-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59668-104">Syntax</span></span>  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59668-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59668-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="59668-106">[out] Un valor de enumeración de CorDebugRegister que indica el registro de una variable con un tipo de ubicación de `VLT_REGISTER`y el registro de base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="59668-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59668-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="59668-107">Return Value</span></span>  
 <span data-ttu-id="59668-108">El método devuelve los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="59668-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="59668-109">Valor</span><span class="sxs-lookup"><span data-stu-id="59668-109">Value</span></span>|<span data-ttu-id="59668-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="59668-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="59668-111">La variable está en el registro indicado por la `pRegister` argumento.</span><span class="sxs-lookup"><span data-stu-id="59668-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="59668-112">La variable no está en un registro o una ubicación relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="59668-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59668-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59668-113">Requirements</span></span>  
 <span data-ttu-id="59668-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59668-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59668-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59668-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59668-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59668-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59668-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59668-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59668-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="59668-118">See Also</span></span>  
 [<span data-ttu-id="59668-119">VariableLocationType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="59668-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 [<span data-ttu-id="59668-120">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="59668-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
