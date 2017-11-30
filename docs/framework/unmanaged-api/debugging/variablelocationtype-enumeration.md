---
title: "VariableLocationType (enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: VariableLocationType
api_location: mscordbi.dll
api_type: COM
f1_keywords: VariableLocationType
helpviewer_keywords: VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0338a89acdd9c29370bc8e52ed9a099e9330c2cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="c93eb-102">VariableLocationType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="c93eb-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="c93eb-103">Indica el tipo de ubicación nativo de una variable.</span><span class="sxs-lookup"><span data-stu-id="c93eb-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c93eb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c93eb-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="c93eb-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c93eb-105">Members</span></span>  
  
|<span data-ttu-id="c93eb-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c93eb-106">Member</span></span>|<span data-ttu-id="c93eb-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c93eb-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="c93eb-108">La variable está en un registro.</span><span class="sxs-lookup"><span data-stu-id="c93eb-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="c93eb-109">La variable está en una ubicación de memoria relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="c93eb-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="c93eb-110">La variable no se almacena en un registro o una ubicación de memoria relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="c93eb-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c93eb-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c93eb-111">Remarks</span></span>  
 <span data-ttu-id="c93eb-112">Un miembro de la `VariableLocationType` enumeración devuelto por la [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="c93eb-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c93eb-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c93eb-113">Requirements</span></span>  
 <span data-ttu-id="c93eb-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c93eb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c93eb-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c93eb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c93eb-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c93eb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c93eb-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c93eb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c93eb-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c93eb-118">See Also</span></span>  
 [<span data-ttu-id="c93eb-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="c93eb-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
