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
ms.openlocfilehash: 1aa59ee559abff8006f0ac63a812e4315aa48154
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790309"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="7dcae-102">Enumeración VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="7dcae-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="7dcae-103">Indica el tipo de ubicación nativa de una variable.</span><span class="sxs-lookup"><span data-stu-id="7dcae-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dcae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7dcae-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="7dcae-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="7dcae-105">Members</span></span>  
  
|<span data-ttu-id="7dcae-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="7dcae-106">Member</span></span>|<span data-ttu-id="7dcae-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7dcae-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="7dcae-108">La variable está en un registro.</span><span class="sxs-lookup"><span data-stu-id="7dcae-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="7dcae-109">La variable está en una ubicación de memoria relativa de registro.</span><span class="sxs-lookup"><span data-stu-id="7dcae-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="7dcae-110">La variable no se almacena en un registro o en una ubicación de memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="7dcae-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dcae-111">Notas</span><span class="sxs-lookup"><span data-stu-id="7dcae-111">Remarks</span></span>  
 <span data-ttu-id="7dcae-112">El método [ICorDebugVariableHome:: GetLocationType](icordebugvariablehome-getlocationtype-method.md) devuelve un miembro de la enumeración `VariableLocationType`.</span><span class="sxs-lookup"><span data-stu-id="7dcae-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dcae-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="7dcae-113">Requirements</span></span>  
 <span data-ttu-id="7dcae-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dcae-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dcae-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7dcae-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7dcae-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7dcae-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7dcae-117">**.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dcae-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dcae-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dcae-118">See also</span></span>

- [<span data-ttu-id="7dcae-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="7dcae-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
