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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca922d8b582c0608073d4fd0ba986167ae470e34
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109673"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="beb24-102">CorDebugNGenPolicy (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="beb24-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="beb24-103">Proporciona un valor que determina si un depurador carga imágenes nativas (NGen) desde la caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="beb24-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beb24-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="beb24-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="beb24-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="beb24-105">Members</span></span>  
  
|<span data-ttu-id="beb24-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="beb24-106">Member name</span></span>|<span data-ttu-id="beb24-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="beb24-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="beb24-108">En un [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] aplicación, el uso de imágenes de la memoria caché de imágenes nativas local está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="beb24-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="beb24-109">En una aplicación de escritorio, esta configuración no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="beb24-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="beb24-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="beb24-110">Remarks</span></span>  
 <span data-ttu-id="beb24-111">El `CorDebugNGENPolicy` enumeración la utiliza el [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="beb24-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="beb24-112">Deshabilitar el uso de imágenes de la memoria caché de imágenes nativas local proporciona una experiencia de depuración coherente asegurándose de que el depurador carga imágenes depurables compilado JIT en lugar de las imágenes nativas optimizadas.</span><span class="sxs-lookup"><span data-stu-id="beb24-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beb24-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="beb24-113">Requirements</span></span>  
 <span data-ttu-id="beb24-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beb24-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beb24-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="beb24-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="beb24-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beb24-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="beb24-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beb24-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beb24-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="beb24-118">See also</span></span>

- [<span data-ttu-id="beb24-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="beb24-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
