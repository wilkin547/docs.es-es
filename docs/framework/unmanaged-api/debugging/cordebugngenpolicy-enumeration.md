---
title: CorDebugNGenPolicy (enumeración)
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
ms.openlocfilehash: 2f8337f96239948189ffd58923d87fd05c79b0c3
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204862"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="ca76a-102">CorDebugNGenPolicy (enumeración)</span><span class="sxs-lookup"><span data-stu-id="ca76a-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="ca76a-103">Proporciona un valor que determina si un depurador carga imágenes nativas (NGen) desde la caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="ca76a-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca76a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca76a-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="ca76a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ca76a-105">Members</span></span>  
  
|<span data-ttu-id="ca76a-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="ca76a-106">Member name</span></span>|<span data-ttu-id="ca76a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca76a-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="ca76a-108">En una aplicación de la tienda Windows 8. x, el uso de imágenes de la memoria caché de imágenes nativas local está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="ca76a-108">In a Windows 8.x Store app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="ca76a-109">En una aplicación de escritorio, este valor no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="ca76a-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca76a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca76a-110">Remarks</span></span>  
 <span data-ttu-id="ca76a-111">El método [ICorDebugProcess5:: enablengenpolicy (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) usa la enumeración `CorDebugNGENPolicy`.</span><span class="sxs-lookup"><span data-stu-id="ca76a-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="ca76a-112">Deshabilitar el uso de imágenes de la memoria caché de imágenes nativas local proporciona una experiencia de depuración coherente asegurándose de que el depurador carga imágenes compiladas por JIT depurables en lugar de imágenes nativas optimizadas.</span><span class="sxs-lookup"><span data-stu-id="ca76a-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca76a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca76a-113">Requirements</span></span>  
 <span data-ttu-id="ca76a-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca76a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca76a-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca76a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca76a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca76a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca76a-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca76a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca76a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca76a-118">See also</span></span>

- [<span data-ttu-id="ca76a-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="ca76a-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
