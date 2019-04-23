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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 392254efcd099aca60e58b3cc0bc61ca85aa2c66
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099955"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="267e4-102">Enumeración VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="267e4-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="267e4-103">Indica el tipo de ubicación nativa de una variable.</span><span class="sxs-lookup"><span data-stu-id="267e4-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="267e4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="267e4-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="267e4-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="267e4-105">Members</span></span>  
  
|<span data-ttu-id="267e4-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="267e4-106">Member</span></span>|<span data-ttu-id="267e4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="267e4-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="267e4-108">La variable está en un registro.</span><span class="sxs-lookup"><span data-stu-id="267e4-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="267e4-109">La variable está en una ubicación de memoria relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="267e4-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="267e4-110">La variable no se almacena en un registro o una ubicación de memoria relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="267e4-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="267e4-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="267e4-111">Remarks</span></span>  
 <span data-ttu-id="267e4-112">Un miembro de la `VariableLocationType` enumeración devuelta por la [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="267e4-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="267e4-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="267e4-113">Requirements</span></span>  
 <span data-ttu-id="267e4-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="267e4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="267e4-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="267e4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="267e4-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="267e4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="267e4-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="267e4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="267e4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="267e4-118">See also</span></span>

- [<span data-ttu-id="267e4-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="267e4-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
