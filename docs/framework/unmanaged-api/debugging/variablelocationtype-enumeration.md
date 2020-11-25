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
ms.openlocfilehash: 1c65efa006a8b2f4fb4db257b4ad2cde99c4e75e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725266"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="f2d6a-102">Enumeración VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="f2d6a-102">VariableLocationType Enumeration</span></span>

<span data-ttu-id="f2d6a-103">Indica el tipo de ubicación nativa de una variable.</span><span class="sxs-lookup"><span data-stu-id="f2d6a-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2d6a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2d6a-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="f2d6a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f2d6a-105">Members</span></span>  
  
|<span data-ttu-id="f2d6a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f2d6a-106">Member</span></span>|<span data-ttu-id="f2d6a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2d6a-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="f2d6a-108">La variable está en un registro.</span><span class="sxs-lookup"><span data-stu-id="f2d6a-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="f2d6a-109">La variable está en una ubicación de memoria relativa de registro.</span><span class="sxs-lookup"><span data-stu-id="f2d6a-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="f2d6a-110">La variable no se almacena en un registro o en una ubicación de memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="f2d6a-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2d6a-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f2d6a-111">Remarks</span></span>  

 <span data-ttu-id="f2d6a-112">`VariableLocationType`El método [ICorDebugVariableHome:: GetLocationType](icordebugvariablehome-getlocationtype-method.md) devuelve un miembro de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="f2d6a-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2d6a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2d6a-113">Requirements</span></span>  

 <span data-ttu-id="f2d6a-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2d6a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2d6a-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2d6a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2d6a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2d6a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2d6a-117">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2d6a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2d6a-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2d6a-118">See also</span></span>

- [<span data-ttu-id="f2d6a-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="f2d6a-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
