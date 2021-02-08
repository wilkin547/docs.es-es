---
description: 'Más información sobre: enumeración Cordebugcreateprocessflags ('
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
ms.openlocfilehash: 29363510c83873c7f367079857809c165bc55b1e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801740"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="8c134-103">CorDebugCreateProcessFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8c134-103">CorDebugCreateProcessFlags Enumeration</span></span>

<span data-ttu-id="8c134-104">Proporciona opciones de depuración adicionales que se pueden usar en una llamada al método [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8c134-104">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c134-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c134-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="8c134-106">Members</span><span class="sxs-lookup"><span data-stu-id="8c134-106">Members</span></span>  
  
|<span data-ttu-id="8c134-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="8c134-107">Member</span></span>|<span data-ttu-id="8c134-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c134-108">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="8c134-109">No se establece ninguna opción especial.</span><span class="sxs-lookup"><span data-stu-id="8c134-109">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c134-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c134-110">Requirements</span></span>  

 <span data-ttu-id="8c134-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c134-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c134-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c134-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c134-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c134-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c134-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c134-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c134-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c134-115">See also</span></span>

- [<span data-ttu-id="8c134-116">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="8c134-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
