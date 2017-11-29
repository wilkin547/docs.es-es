---
title: "CorDebugIlToNativeMappingTypes (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugIlToNativeMappingTypes
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugIlToNativeMappingTypes
helpviewer_keywords: CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 03046ebb678df64ad3d151aaadba313645417979
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="5c33c-102">CorDebugIlToNativeMappingTypes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="5c33c-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="5c33c-103">Indica si un intervalo determinado de instrucciones nativas, representado por una instancia de la estructura COR_DEBUG_IL_TO_NATIVE_MAP, corresponde a una región de código especial.</span><span class="sxs-lookup"><span data-stu-id="5c33c-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c33c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c33c-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="5c33c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5c33c-105">Members</span></span>  
  
|<span data-ttu-id="5c33c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5c33c-106">Member</span></span>|<span data-ttu-id="5c33c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c33c-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="5c33c-108">El intervalo de instrucciones nativas no corresponde a ninguna región de código especial.</span><span class="sxs-lookup"><span data-stu-id="5c33c-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="5c33c-109">El intervalo de instrucciones nativas corresponde al prólogo.</span><span class="sxs-lookup"><span data-stu-id="5c33c-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="5c33c-110">El intervalo de instrucciones nativas se corresponde con el epílogo.</span><span class="sxs-lookup"><span data-stu-id="5c33c-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5c33c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c33c-111">Requirements</span></span>  
 <span data-ttu-id="5c33c-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c33c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c33c-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c33c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c33c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c33c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c33c-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c33c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c33c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c33c-116">See Also</span></span>  
 [<span data-ttu-id="5c33c-117">GetILToNativeMapping (método)</span><span class="sxs-lookup"><span data-stu-id="5c33c-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)  
 [<span data-ttu-id="5c33c-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="5c33c-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
