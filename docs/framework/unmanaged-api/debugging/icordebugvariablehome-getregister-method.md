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
ms.openlocfilehash: 290647f0e0dcaeae53362762ed7f8e0c2f05a82c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189955"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="2638f-102">Método ICorDebugVariableHome::GetRegister</span><span class="sxs-lookup"><span data-stu-id="2638f-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="2638f-103">Obtiene el registro que contiene una variable con un tipo de ubicación de `VLT_REGISTER`y el registro de base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="2638f-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2638f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2638f-104">Syntax</span></span>  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2638f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2638f-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="2638f-106">[out] Un valor de enumeración CorDebugRegister que indica el registro de una variable con un tipo de ubicación de `VLT_REGISTER`y el registro de base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="2638f-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2638f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2638f-107">Return Value</span></span>  
 <span data-ttu-id="2638f-108">El método devuelve los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="2638f-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="2638f-109">Valor</span><span class="sxs-lookup"><span data-stu-id="2638f-109">Value</span></span>|<span data-ttu-id="2638f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2638f-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="2638f-111">La variable está en el registro indicado por la `pRegister` argumento.</span><span class="sxs-lookup"><span data-stu-id="2638f-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="2638f-112">La variable no está en un registro o una ubicación relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="2638f-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2638f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2638f-113">Requirements</span></span>  
 <span data-ttu-id="2638f-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2638f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2638f-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2638f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2638f-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2638f-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2638f-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2638f-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2638f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2638f-118">See also</span></span>

- [<span data-ttu-id="2638f-119">Enumeración VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="2638f-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
- [<span data-ttu-id="2638f-120">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="2638f-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
