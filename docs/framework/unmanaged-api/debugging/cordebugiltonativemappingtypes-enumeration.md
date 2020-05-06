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
ms.openlocfilehash: 808fc70a308eff1b05aa49ea2bb89fe53377c973
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795851"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="205ce-102">CorDebugIlToNativeMappingTypes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="205ce-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="205ce-103">Indica si un determinado intervalo de instrucciones nativas, representado por una instancia de la estructura COR_DEBUG_IL_TO_NATIVE_MAP, corresponde a una región de código especial.</span><span class="sxs-lookup"><span data-stu-id="205ce-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="205ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="205ce-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="205ce-105">Members</span><span class="sxs-lookup"><span data-stu-id="205ce-105">Members</span></span>  
  
|<span data-ttu-id="205ce-106">Member</span><span class="sxs-lookup"><span data-stu-id="205ce-106">Member</span></span>|<span data-ttu-id="205ce-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="205ce-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="205ce-108">El intervalo de instrucciones nativas no se corresponde con ninguna región de código especial.</span><span class="sxs-lookup"><span data-stu-id="205ce-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="205ce-109">El intervalo de instrucciones nativas corresponde al prólogo.</span><span class="sxs-lookup"><span data-stu-id="205ce-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="205ce-110">El intervalo de instrucciones nativas corresponde al epílogo.</span><span class="sxs-lookup"><span data-stu-id="205ce-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="205ce-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="205ce-111">Requirements</span></span>  
 <span data-ttu-id="205ce-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="205ce-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="205ce-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="205ce-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="205ce-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="205ce-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="205ce-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="205ce-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="205ce-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="205ce-116">See also</span></span>

- [<span data-ttu-id="205ce-117">Método GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="205ce-117">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="205ce-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="205ce-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
