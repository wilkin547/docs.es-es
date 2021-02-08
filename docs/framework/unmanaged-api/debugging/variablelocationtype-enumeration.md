---
description: 'Más información sobre: enumeración VariableLocationType'
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
ms.openlocfilehash: 8561077b9f3f4d318eeb743d51538b2a9a22a217
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800531"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="ba0f5-103">Enumeración VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="ba0f5-103">VariableLocationType Enumeration</span></span>

<span data-ttu-id="ba0f5-104">Indica el tipo de ubicación nativa de una variable.</span><span class="sxs-lookup"><span data-stu-id="ba0f5-104">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba0f5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba0f5-105">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="ba0f5-106">Members</span><span class="sxs-lookup"><span data-stu-id="ba0f5-106">Members</span></span>  
  
|<span data-ttu-id="ba0f5-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="ba0f5-107">Member</span></span>|<span data-ttu-id="ba0f5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba0f5-108">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="ba0f5-109">La variable está en un registro.</span><span class="sxs-lookup"><span data-stu-id="ba0f5-109">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="ba0f5-110">La variable está en una ubicación de memoria relativa de registro.</span><span class="sxs-lookup"><span data-stu-id="ba0f5-110">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="ba0f5-111">La variable no se almacena en un registro o en una ubicación de memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="ba0f5-111">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba0f5-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ba0f5-112">Remarks</span></span>  

 <span data-ttu-id="ba0f5-113">`VariableLocationType`El método [ICorDebugVariableHome:: GetLocationType](icordebugvariablehome-getlocationtype-method.md) devuelve un miembro de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="ba0f5-113">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba0f5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba0f5-114">Requirements</span></span>  

 <span data-ttu-id="ba0f5-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba0f5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba0f5-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba0f5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba0f5-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba0f5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba0f5-118">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba0f5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba0f5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba0f5-119">See also</span></span>

- [<span data-ttu-id="ba0f5-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="ba0f5-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
