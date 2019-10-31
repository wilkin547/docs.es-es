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
# <a name="cordebugplatform-enumeration"></a>CorDebugPlatform (Enumeración)
Proporciona valores de plataforma de destino utilizados por el método [ICorDebugDataTarget:: GetPlatform (](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
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
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|CORDB_PLATFORM_WINDOWS_X86|La plataforma de destino es Windows ejecutándose en hardware Intel x86.|  
|CORDB_PLATFORM_WINDOWS_AMD64|La plataforma de destino es Windows de 64 bits ejecutándose en hardware AMD64 o Intel EM64T.|  
|CORDB_PLATFORM_WINDOWS_IA64|La plataforma de destino es Windows de 32 bits ejecutándose en hardware IA-64.|  
|CORDB_PLATFORM_MAC_PPC|La plataforma de destino es el sistema operativo Macintosh que se ejecuta en hardware PowerPC.|  
|CORDB_PLATFORM_MAC_X86|La plataforma de destino es el sistema operativo Macintosh que se ejecuta en hardware Intel x86.|  
|CORDB_PLATFORM_WINDOWS_ARM|La plataforma de destino es el sistema operativo Macintosh que se ejecuta en hardware ARM de Windows.|  
|CORDB_PLATFORM_MAC_AMD64|La plataforma de destino es el sistema operativo Macintosh que se ejecuta en hardware AMD64.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
 Los miembros `CORDB_PLATFORM_WINDOWS_ARM` y `CORDB_PLATFORM_MAC_AMD64` están disponible en .NET Framework 4.5.2 y versiones posteriores.  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
