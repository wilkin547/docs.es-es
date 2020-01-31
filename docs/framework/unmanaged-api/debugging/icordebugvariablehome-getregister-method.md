---
title: 'ICorDebugVariableHome:: GetRegister (método)'
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
ms.openlocfilehash: 396dd9c017fca6dc7037b43355ba7f726d7390ea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790986"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="267cc-102">ICorDebugVariableHome:: GetRegister (método)</span><span class="sxs-lookup"><span data-stu-id="267cc-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="267cc-103">Obtiene el registro que contiene una variable con un tipo de ubicación de `VLT_REGISTER`y el registro base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="267cc-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="267cc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="267cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="267cc-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="267cc-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="267cc-106">enuncia Un valor de enumeración CorDebugRegister (que indica el registro de una variable con un tipo de ubicación de `VLT_REGISTER`y el registro base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="267cc-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="267cc-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="267cc-107">Return Value</span></span>  
 <span data-ttu-id="267cc-108">El método devuelve los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="267cc-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="267cc-109">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="267cc-109">Value</span></span>|<span data-ttu-id="267cc-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="267cc-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="267cc-111">La variable está en el registro indicado por el argumento `pRegister`.</span><span class="sxs-lookup"><span data-stu-id="267cc-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="267cc-112">La variable no está en un registro o en una ubicación relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="267cc-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="267cc-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="267cc-113">Requirements</span></span>  
 <span data-ttu-id="267cc-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="267cc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="267cc-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="267cc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="267cc-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="267cc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="267cc-117">**.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="267cc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="267cc-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="267cc-118">See also</span></span>

- [<span data-ttu-id="267cc-119">VariableLocationType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="267cc-119">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
- [<span data-ttu-id="267cc-120">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="267cc-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
