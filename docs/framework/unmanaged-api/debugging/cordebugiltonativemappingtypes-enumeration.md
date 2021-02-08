---
description: 'Más información sobre: enumeración CorDebugIlToNativeMappingTypes ('
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
ms.openlocfilehash: bcca11bf3c7574fe76684f6786d7408c80acfa43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801640"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="0c29b-103">CorDebugIlToNativeMappingTypes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0c29b-103">CorDebugIlToNativeMappingTypes Enumeration</span></span>

<span data-ttu-id="0c29b-104">Indica si un determinado intervalo de instrucciones nativas, representado por una instancia de la estructura COR_DEBUG_IL_TO_NATIVE_MAP, corresponde a una región de código especial.</span><span class="sxs-lookup"><span data-stu-id="0c29b-104">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c29b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c29b-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="0c29b-106">Members</span><span class="sxs-lookup"><span data-stu-id="0c29b-106">Members</span></span>  
  
|<span data-ttu-id="0c29b-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="0c29b-107">Member</span></span>|<span data-ttu-id="0c29b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c29b-108">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="0c29b-109">El intervalo de instrucciones nativas no se corresponde con ninguna región de código especial.</span><span class="sxs-lookup"><span data-stu-id="0c29b-109">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="0c29b-110">El intervalo de instrucciones nativas corresponde al prólogo.</span><span class="sxs-lookup"><span data-stu-id="0c29b-110">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="0c29b-111">El intervalo de instrucciones nativas corresponde al epílogo.</span><span class="sxs-lookup"><span data-stu-id="0c29b-111">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c29b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c29b-112">Requirements</span></span>  

 <span data-ttu-id="0c29b-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c29b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c29b-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c29b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c29b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c29b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c29b-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c29b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c29b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c29b-117">See also</span></span>

- [<span data-ttu-id="0c29b-118">Método GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="0c29b-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="0c29b-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="0c29b-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
