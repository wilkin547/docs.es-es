---
title: CorDebugPlatform (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugPlatformEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugPlatformEnum
helpviewer_keywords:
- CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8cbf09ab4ad0192902a964d55a050685b024284
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574305"
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="28bb9-102">CorDebugPlatform (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="28bb9-102">CorDebugPlatform Enumeration</span></span>
<span data-ttu-id="28bb9-103">Proporciona valores de plataforma de destino que se usan por el [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="28bb9-103">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28bb9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28bb9-104">Syntax</span></span>  
  
```  
typedef enum CorDebugPlatform  
{  
    CORDB_PLATFORM_WINDOWS_X86,    // Windows on Intel x86  
    CORDB_PLATFORM_WINDOWS_AMD64,  // Windows x64 (AMD64, Intel EM64T)  
    CORDB_PLATFORM_WINDOWS_IA64,   // Windows on Intel IA-64  
    CORDB_PLATFORM_MAC_PPC,        // Macintosh OS on PowerPC  
    CORDB_PLATFORM_MAC_X86,        // Macintosh OS on Intel x86  
    CORDB_PLATFORM_WINDOWS_ARM,    // Windows on ARM  
    CORDB_PLATFORM_MAC_AMD64       // MacOS on Intel x64  
} CorDebugPlatform;  
```  
  
## <a name="members"></a><span data-ttu-id="28bb9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="28bb9-105">Members</span></span>  
  
|<span data-ttu-id="28bb9-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="28bb9-106">Member</span></span>|<span data-ttu-id="28bb9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="28bb9-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="28bb9-108">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="28bb9-108">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="28bb9-109">La plataforma de destino es Windows ejecutándose en hardware Intel x86.</span><span class="sxs-lookup"><span data-stu-id="28bb9-109">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="28bb9-110">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="28bb9-110">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="28bb9-111">La plataforma de destino es Windows de 64 bits ejecutándose en hardware AMD64 o Intel EM64T.</span><span class="sxs-lookup"><span data-stu-id="28bb9-111">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="28bb9-112">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="28bb9-112">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="28bb9-113">La plataforma de destino es Windows de 32 bits ejecutándose en hardware IA-64.</span><span class="sxs-lookup"><span data-stu-id="28bb9-113">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="28bb9-114">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="28bb9-114">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="28bb9-115">La plataforma de destino es el sistema operativo Macintosh que se ejecuta en hardware PowerPC.</span><span class="sxs-lookup"><span data-stu-id="28bb9-115">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="28bb9-116">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="28bb9-116">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="28bb9-117">La plataforma de destino es el sistema operativo Macintosh ejecutándose en hardware Intel x86.</span><span class="sxs-lookup"><span data-stu-id="28bb9-117">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="28bb9-118">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="28bb9-118">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="28bb9-119">La plataforma de destino es el sistema operativo Macintosh que se ejecutan en hardware Windows ARM.</span><span class="sxs-lookup"><span data-stu-id="28bb9-119">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="28bb9-120">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="28bb9-120">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="28bb9-121">La plataforma de destino es el sistema operativo Macintosh ejecutándose en hardware AMD64.</span><span class="sxs-lookup"><span data-stu-id="28bb9-121">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28bb9-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28bb9-122">Requirements</span></span>  
 <span data-ttu-id="28bb9-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28bb9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28bb9-124">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28bb9-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28bb9-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28bb9-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28bb9-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28bb9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="28bb9-127">Los miembros `CORDB_PLATFORM_WINDOWS_ARM` y `CORDB_PLATFORM_MAC_AMD64` están disponible en .NET Framework 4.5.2 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="28bb9-127">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28bb9-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="28bb9-128">See also</span></span>
- [<span data-ttu-id="28bb9-129">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="28bb9-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
