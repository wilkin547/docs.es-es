---
description: 'Más información sobre: enumeración Cordebugplatform ('
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
ms.openlocfilehash: d6a78ec00f99ff34158f784e039372c8937e6d16
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661862"
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="c1a62-103">CorDebugPlatform (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c1a62-103">CorDebugPlatform Enumeration</span></span>

<span data-ttu-id="c1a62-104">Proporciona valores de plataforma de destino utilizados por el método [ICorDebugDataTarget:: GetPlatform (](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c1a62-104">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1a62-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1a62-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c1a62-106">Members</span><span class="sxs-lookup"><span data-stu-id="c1a62-106">Members</span></span>  
  
|<span data-ttu-id="c1a62-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="c1a62-107">Member</span></span>|<span data-ttu-id="c1a62-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1a62-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c1a62-109">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="c1a62-109">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="c1a62-110">La plataforma de destino es Windows ejecutándose en hardware Intel x86.</span><span class="sxs-lookup"><span data-stu-id="c1a62-110">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="c1a62-111">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="c1a62-111">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="c1a62-112">La plataforma de destino es Windows de 64 bits ejecutándose en hardware AMD64 o Intel EM64T.</span><span class="sxs-lookup"><span data-stu-id="c1a62-112">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="c1a62-113">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="c1a62-113">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="c1a62-114">La plataforma de destino es Windows de 32 bits ejecutándose en hardware IA-64.</span><span class="sxs-lookup"><span data-stu-id="c1a62-114">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="c1a62-115">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="c1a62-115">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="c1a62-116">La plataforma de destino es el sistema operativo Macintosh que se ejecuta en hardware PowerPC.</span><span class="sxs-lookup"><span data-stu-id="c1a62-116">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="c1a62-117">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="c1a62-117">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="c1a62-118">La plataforma de destino es el sistema operativo Macintosh que se ejecuta en hardware Intel x86.</span><span class="sxs-lookup"><span data-stu-id="c1a62-118">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="c1a62-119">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="c1a62-119">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="c1a62-120">La plataforma de destino es el sistema operativo Macintosh que se ejecuta en hardware ARM de Windows.</span><span class="sxs-lookup"><span data-stu-id="c1a62-120">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="c1a62-121">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="c1a62-121">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="c1a62-122">La plataforma de destino es el sistema operativo Macintosh que se ejecuta en hardware AMD64.</span><span class="sxs-lookup"><span data-stu-id="c1a62-122">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c1a62-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1a62-123">Requirements</span></span>  

 <span data-ttu-id="c1a62-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1a62-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1a62-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1a62-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1a62-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1a62-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1a62-127">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1a62-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="c1a62-128">Los miembros `CORDB_PLATFORM_WINDOWS_ARM` y `CORDB_PLATFORM_MAC_AMD64` están disponible en .NET Framework 4.5.2 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="c1a62-128">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a62-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1a62-129">See also</span></span>

- [<span data-ttu-id="c1a62-130">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="c1a62-130">Debugging Enumerations</span></span>](debugging-enumerations.md)
