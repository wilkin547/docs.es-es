---
title: Método ICorDebugVariableHome::GetRegister
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73ab94765e1b76cb8521a0d546d6bc61384aad5f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480746"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="f2043-102">Método ICorDebugVariableHome::GetRegister</span><span class="sxs-lookup"><span data-stu-id="f2043-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="f2043-103">Obtiene el registro que contiene una variable con un tipo de ubicación de `VLT_REGISTER`y el registro de base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="f2043-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2043-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2043-104">Syntax</span></span>  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2043-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2043-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="f2043-106">[out] Un valor de enumeración CorDebugRegister que indica el registro de una variable con un tipo de ubicación de `VLT_REGISTER`y el registro de base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="f2043-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2043-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f2043-107">Return Value</span></span>  
 <span data-ttu-id="f2043-108">El método devuelve los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="f2043-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="f2043-109">Valor</span><span class="sxs-lookup"><span data-stu-id="f2043-109">Value</span></span>|<span data-ttu-id="f2043-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2043-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="f2043-111">La variable está en el registro indicado por la `pRegister` argumento.</span><span class="sxs-lookup"><span data-stu-id="f2043-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="f2043-112">La variable no está en un registro o una ubicación relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="f2043-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2043-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2043-113">Requirements</span></span>  
 <span data-ttu-id="f2043-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2043-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2043-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2043-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2043-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2043-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2043-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2043-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2043-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2043-118">See also</span></span>
- [<span data-ttu-id="f2043-119">VariableLocationType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="f2043-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
- [<span data-ttu-id="f2043-120">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2043-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
