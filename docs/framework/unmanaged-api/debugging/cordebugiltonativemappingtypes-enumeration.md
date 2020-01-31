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
ms.openlocfilehash: ddb5af486ab6fb1c8c4fabf3ccf7b43d037e1eeb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789318"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="9569e-102">CorDebugIlToNativeMappingTypes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9569e-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="9569e-103">Indica si un determinado intervalo de instrucciones nativas, representado por una instancia de la estructura COR_DEBUG_IL_TO_NATIVE_MAP, corresponde a una región de código especial.</span><span class="sxs-lookup"><span data-stu-id="9569e-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9569e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9569e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="9569e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9569e-105">Members</span></span>  
  
|<span data-ttu-id="9569e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9569e-106">Member</span></span>|<span data-ttu-id="9569e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9569e-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="9569e-108">El intervalo de instrucciones nativas no se corresponde con ninguna región de código especial.</span><span class="sxs-lookup"><span data-stu-id="9569e-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="9569e-109">El intervalo de instrucciones nativas corresponde al prólogo.</span><span class="sxs-lookup"><span data-stu-id="9569e-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="9569e-110">El intervalo de instrucciones nativas corresponde al epílogo.</span><span class="sxs-lookup"><span data-stu-id="9569e-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9569e-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="9569e-111">Requirements</span></span>  
 <span data-ttu-id="9569e-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9569e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9569e-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9569e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9569e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9569e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9569e-115">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9569e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9569e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9569e-116">See also</span></span>

- [<span data-ttu-id="9569e-117">GetILToNativeMapping (método)</span><span class="sxs-lookup"><span data-stu-id="9569e-117">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="9569e-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="9569e-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
