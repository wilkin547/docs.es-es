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
ms.openlocfilehash: 5d66503487e1b997e2b8cc7d3d46e210a4dbbe05
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132763"
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="1cbec-102">CorDebugPlatform (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1cbec-102">CorDebugPlatform Enumeration</span></span>
<span data-ttu-id="1cbec-103">Proporciona valores de plataforma de destino utilizados por el método [ICorDebugDataTarget:: GetPlatform (](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1cbec-103">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cbec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1cbec-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="1cbec-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="1cbec-105">Members</span></span>  
  
|<span data-ttu-id="1cbec-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="1cbec-106">Member</span></span>|<span data-ttu-id="1cbec-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1cbec-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1cbec-108">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="1cbec-108">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="1cbec-109">La plataforma de destino es Windows ejecutándose en hardware Intel x86.</span><span class="sxs-lookup"><span data-stu-id="1cbec-109">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="1cbec-110">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="1cbec-110">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="1cbec-111">La plataforma de destino es Windows de 64 bits ejecutándose en hardware AMD64 o Intel EM64T.</span><span class="sxs-lookup"><span data-stu-id="1cbec-111">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="1cbec-112">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="1cbec-112">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="1cbec-113">La plataforma de destino es Windows de 32 bits ejecutándose en hardware IA-64.</span><span class="sxs-lookup"><span data-stu-id="1cbec-113">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="1cbec-114">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="1cbec-114">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="1cbec-115">La plataforma de destino es el sistema operativo Macintosh que se ejecuta en hardware PowerPC.</span><span class="sxs-lookup"><span data-stu-id="1cbec-115">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="1cbec-116">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="1cbec-116">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="1cbec-117">La plataforma de destino es el sistema operativo Macintosh que se ejecuta en hardware Intel x86.</span><span class="sxs-lookup"><span data-stu-id="1cbec-117">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="1cbec-118">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="1cbec-118">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="1cbec-119">La plataforma de destino es el sistema operativo Macintosh que se ejecuta en hardware ARM de Windows.</span><span class="sxs-lookup"><span data-stu-id="1cbec-119">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="1cbec-120">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="1cbec-120">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="1cbec-121">La plataforma de destino es el sistema operativo Macintosh que se ejecuta en hardware AMD64.</span><span class="sxs-lookup"><span data-stu-id="1cbec-121">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1cbec-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1cbec-122">Requirements</span></span>  
 <span data-ttu-id="1cbec-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cbec-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cbec-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1cbec-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1cbec-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cbec-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cbec-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cbec-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="1cbec-127">Los miembros `CORDB_PLATFORM_WINDOWS_ARM` y `CORDB_PLATFORM_MAC_AMD64` están disponible en .NET Framework 4.5.2 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="1cbec-127">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cbec-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cbec-128">See also</span></span>

- [<span data-ttu-id="1cbec-129">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="1cbec-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
