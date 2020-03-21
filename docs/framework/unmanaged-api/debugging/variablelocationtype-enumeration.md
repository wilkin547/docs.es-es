---
title: Enumeración VariableLocationType
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
ms.openlocfilehash: e2fa5d5a998f51e0e90cfde22b40ec12f278307b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178356"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="131cf-102">Enumeración VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="131cf-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="131cf-103">Indica el tipo de ubicación nativa de una variable.</span><span class="sxs-lookup"><span data-stu-id="131cf-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="131cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="131cf-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="131cf-105">Members</span><span class="sxs-lookup"><span data-stu-id="131cf-105">Members</span></span>  
  
|<span data-ttu-id="131cf-106">Member</span><span class="sxs-lookup"><span data-stu-id="131cf-106">Member</span></span>|<span data-ttu-id="131cf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="131cf-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="131cf-108">La variable está en un registro.</span><span class="sxs-lookup"><span data-stu-id="131cf-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="131cf-109">La variable se encuentra en una ubicación de memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="131cf-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="131cf-110">La variable no se almacena en un registro o en una ubicación de memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="131cf-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="131cf-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="131cf-111">Remarks</span></span>  
 <span data-ttu-id="131cf-112">Un miembro `VariableLocationType` de la enumeración es devuelto por el [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="131cf-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="131cf-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="131cf-113">Requirements</span></span>  
 <span data-ttu-id="131cf-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="131cf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="131cf-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="131cf-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="131cf-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="131cf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="131cf-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="131cf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="131cf-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="131cf-118">See also</span></span>

- [<span data-ttu-id="131cf-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="131cf-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
