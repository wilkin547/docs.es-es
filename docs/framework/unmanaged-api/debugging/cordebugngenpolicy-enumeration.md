---
title: CorDebugNGenPolicy (Enumeración)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
ms.openlocfilehash: 826dfceb28512e4fd3157c432b7a4d94fba704fd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097860"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="bfa43-102">CorDebugNGenPolicy (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="bfa43-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="bfa43-103">Proporciona un valor que determina si un depurador carga imágenes nativas (NGen) desde la caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="bfa43-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfa43-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfa43-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="bfa43-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="bfa43-105">Members</span></span>  
  
|<span data-ttu-id="bfa43-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="bfa43-106">Member name</span></span>|<span data-ttu-id="bfa43-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfa43-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="bfa43-108">En una aplicación [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)], el uso de imágenes de la memoria caché de imágenes nativas local está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="bfa43-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="bfa43-109">En una aplicación de escritorio, este valor no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="bfa43-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfa43-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bfa43-110">Remarks</span></span>  
 <span data-ttu-id="bfa43-111">El método [ICorDebugProcess5:: enablengenpolicy (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) usa la enumeración `CorDebugNGENPolicy`.</span><span class="sxs-lookup"><span data-stu-id="bfa43-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="bfa43-112">Deshabilitar el uso de imágenes de la memoria caché de imágenes nativas local proporciona una experiencia de depuración coherente asegurándose de que el depurador carga imágenes compiladas por JIT depurables en lugar de imágenes nativas optimizadas.</span><span class="sxs-lookup"><span data-stu-id="bfa43-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfa43-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bfa43-113">Requirements</span></span>  
 <span data-ttu-id="bfa43-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfa43-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfa43-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bfa43-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfa43-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfa43-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfa43-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfa43-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfa43-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfa43-118">See also</span></span>

- [<span data-ttu-id="bfa43-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="bfa43-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
