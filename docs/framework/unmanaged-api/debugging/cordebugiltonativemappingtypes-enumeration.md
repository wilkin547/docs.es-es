---
title: CorDebugIlToNativeMappingTypes (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fec0f4f31f45847dc092808b2d47c662213e9d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402527"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="212e2-102">CorDebugIlToNativeMappingTypes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="212e2-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="212e2-103">Indica si un intervalo determinado de instrucciones nativas, representado por una instancia de la estructura COR_DEBUG_IL_TO_NATIVE_MAP, corresponde a una región de código especial.</span><span class="sxs-lookup"><span data-stu-id="212e2-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="212e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="212e2-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="212e2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="212e2-105">Members</span></span>  
  
|<span data-ttu-id="212e2-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="212e2-106">Member</span></span>|<span data-ttu-id="212e2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="212e2-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="212e2-108">El intervalo de instrucciones nativas no corresponde a ninguna región de código especial.</span><span class="sxs-lookup"><span data-stu-id="212e2-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="212e2-109">El intervalo de instrucciones nativas corresponde al prólogo.</span><span class="sxs-lookup"><span data-stu-id="212e2-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="212e2-110">El intervalo de instrucciones nativas se corresponde con el epílogo.</span><span class="sxs-lookup"><span data-stu-id="212e2-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="212e2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="212e2-111">Requirements</span></span>  
 <span data-ttu-id="212e2-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="212e2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="212e2-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="212e2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="212e2-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="212e2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="212e2-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="212e2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="212e2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="212e2-116">See Also</span></span>  
 [<span data-ttu-id="212e2-117">GetILToNativeMapping (método)</span><span class="sxs-lookup"><span data-stu-id="212e2-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)  
 [<span data-ttu-id="212e2-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="212e2-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
