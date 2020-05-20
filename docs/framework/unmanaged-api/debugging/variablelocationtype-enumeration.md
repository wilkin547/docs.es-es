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
ms.openlocfilehash: 455fd06dbdbfd5d9753f3d7270647a742751d804
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420661"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="06d1b-102">Enumeración VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="06d1b-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="06d1b-103">Indica el tipo de ubicación nativa de una variable.</span><span class="sxs-lookup"><span data-stu-id="06d1b-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06d1b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06d1b-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="06d1b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="06d1b-105">Members</span></span>  
  
|<span data-ttu-id="06d1b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="06d1b-106">Member</span></span>|<span data-ttu-id="06d1b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="06d1b-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="06d1b-108">La variable está en un registro.</span><span class="sxs-lookup"><span data-stu-id="06d1b-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="06d1b-109">La variable está en una ubicación de memoria relativa de registro.</span><span class="sxs-lookup"><span data-stu-id="06d1b-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="06d1b-110">La variable no se almacena en un registro o en una ubicación de memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="06d1b-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06d1b-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="06d1b-111">Remarks</span></span>  
 <span data-ttu-id="06d1b-112">`VariableLocationType`El método [ICorDebugVariableHome:: GetLocationType](icordebugvariablehome-getlocationtype-method.md) devuelve un miembro de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="06d1b-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06d1b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06d1b-113">Requirements</span></span>  
 <span data-ttu-id="06d1b-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06d1b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06d1b-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06d1b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06d1b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06d1b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06d1b-117">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06d1b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d1b-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="06d1b-118">See also</span></span>

- [<span data-ttu-id="06d1b-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="06d1b-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
