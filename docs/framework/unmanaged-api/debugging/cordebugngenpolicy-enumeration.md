---
title: "CorDebugNGenPolicy (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 89767da7178319ed1add3dda0620062893487bfd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="6d19b-102">CorDebugNGenPolicy (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6d19b-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="6d19b-103">Proporciona un valor que determina si un depurador carga imágenes nativas (NGen) desde la caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="6d19b-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d19b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d19b-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="6d19b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="6d19b-105">Members</span></span>  
  
|<span data-ttu-id="6d19b-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="6d19b-106">Member name</span></span>|<span data-ttu-id="6d19b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d19b-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="6d19b-108">En un [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] aplicación, el uso de imágenes de la caché de imágenes nativas local está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="6d19b-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="6d19b-109">En una aplicación de escritorio, esta configuración no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="6d19b-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d19b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d19b-110">Remarks</span></span>  
 <span data-ttu-id="6d19b-111">El `CorDebugNGENPolicy` enumeración es utilizada por la [icordebugprocess5:: Enablengenpolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="6d19b-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="6d19b-112">Deshabilitar el uso de imágenes de la caché de imágenes nativas local proporciona una experiencia de depuración coherente asegurándose de que el depurador carga imágenes depurables compilado JIT en lugar de las imágenes nativas optimizadas.</span><span class="sxs-lookup"><span data-stu-id="6d19b-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d19b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d19b-113">Requirements</span></span>  
 <span data-ttu-id="6d19b-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d19b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d19b-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d19b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d19b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d19b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d19b-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d19b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d19b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d19b-118">See Also</span></span>  
 [<span data-ttu-id="6d19b-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="6d19b-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
