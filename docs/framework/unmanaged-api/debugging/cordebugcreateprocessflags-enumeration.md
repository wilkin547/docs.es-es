---
title: CorDebugCreateProcessFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugCreateProcessFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugCreateProcessFlags
helpviewer_keywords:
- CorDebugCreateProcessFlags enumeration [.NET Framework debugging]
ms.assetid: e709acce-6a17-4346-b38a-467dba567358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0dfc7da632a5e56f0f6ab6ed55d1e722f49c7e88
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740297"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="dde86-102">CorDebugCreateProcessFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="dde86-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="dde86-103">Proporciona opciones de depuración adicionales que pueden usarse en una llamada a la [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="dde86-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dde86-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dde86-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="dde86-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="dde86-105">Members</span></span>  
  
|<span data-ttu-id="dde86-106">Member</span><span class="sxs-lookup"><span data-stu-id="dde86-106">Member</span></span>|<span data-ttu-id="dde86-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="dde86-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="dde86-108">Se establece ninguna opción especial.</span><span class="sxs-lookup"><span data-stu-id="dde86-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dde86-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dde86-109">Requirements</span></span>  
 <span data-ttu-id="dde86-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dde86-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dde86-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dde86-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dde86-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dde86-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dde86-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dde86-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde86-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dde86-114">See also</span></span>

- [<span data-ttu-id="dde86-115">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="dde86-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
