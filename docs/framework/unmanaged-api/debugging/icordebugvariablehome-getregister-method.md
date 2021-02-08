---
description: 'Más información sobre: ICorDebugVariableHome:: GetRegister (método)'
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
ms.openlocfilehash: c394d455048cf7451b8320ed72a6aa7adfb3518e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790664"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="9fa4b-103">ICorDebugVariableHome:: GetRegister (método)</span><span class="sxs-lookup"><span data-stu-id="9fa4b-103">ICorDebugVariableHome::GetRegister Method</span></span>

<span data-ttu-id="9fa4b-104">Obtiene el registro que contiene una variable con un tipo de ubicación de `VLT_REGISTER` y el registro base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="9fa4b-104">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fa4b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fa4b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fa4b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9fa4b-106">Parameters</span></span>  

 `pRegister`  
 <span data-ttu-id="9fa4b-107">enuncia Un valor de enumeración CorDebugRegister (que indica el registro de una variable con un tipo de ubicación de `VLT_REGISTER` y el registro base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="9fa4b-107">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fa4b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9fa4b-108">Return Value</span></span>  

 <span data-ttu-id="9fa4b-109">El método devuelve los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="9fa4b-109">The method returns the following values:</span></span>  
  
|<span data-ttu-id="9fa4b-110">Value</span><span class="sxs-lookup"><span data-stu-id="9fa4b-110">Value</span></span>|<span data-ttu-id="9fa4b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9fa4b-111">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="9fa4b-112">La variable está en el registro indicado por el `pRegister` argumento.</span><span class="sxs-lookup"><span data-stu-id="9fa4b-112">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="9fa4b-113">La variable no está en un registro o en una ubicación relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="9fa4b-113">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9fa4b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9fa4b-114">Requirements</span></span>  

 <span data-ttu-id="9fa4b-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fa4b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fa4b-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fa4b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fa4b-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fa4b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fa4b-118">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fa4b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fa4b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fa4b-119">See also</span></span>

- [<span data-ttu-id="9fa4b-120">Enumeración VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="9fa4b-120">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
- [<span data-ttu-id="9fa4b-121">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="9fa4b-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
