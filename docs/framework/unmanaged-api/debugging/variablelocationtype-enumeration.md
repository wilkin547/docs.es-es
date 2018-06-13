---
title: VariableLocationType (enumeración)
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
ms.openlocfilehash: 1cc7a299e6be328095c0368acf0a4b767fb74d01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423954"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="669e7-102">VariableLocationType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="669e7-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="669e7-103">Indica el tipo de ubicación nativo de una variable.</span><span class="sxs-lookup"><span data-stu-id="669e7-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="669e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="669e7-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="669e7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="669e7-105">Members</span></span>  
  
|<span data-ttu-id="669e7-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="669e7-106">Member</span></span>|<span data-ttu-id="669e7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="669e7-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="669e7-108">La variable está en un registro.</span><span class="sxs-lookup"><span data-stu-id="669e7-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="669e7-109">La variable está en una ubicación de memoria relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="669e7-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="669e7-110">La variable no se almacena en un registro o una ubicación de memoria relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="669e7-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="669e7-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="669e7-111">Remarks</span></span>  
 <span data-ttu-id="669e7-112">Un miembro de la `VariableLocationType` enumeración devuelto por la [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="669e7-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="669e7-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="669e7-113">Requirements</span></span>  
 <span data-ttu-id="669e7-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="669e7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="669e7-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="669e7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="669e7-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="669e7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="669e7-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="669e7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="669e7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="669e7-118">See Also</span></span>  
 [<span data-ttu-id="669e7-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="669e7-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
