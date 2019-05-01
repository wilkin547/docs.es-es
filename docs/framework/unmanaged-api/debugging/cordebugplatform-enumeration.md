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
ms.openlocfilehash: 03b6f1b29157889d0e84e5dddc94d5e3ae27efce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989643"
---
# <a name="cordebugplatform-enumeration"></a>CorDebugPlatform (Enumeración)
Proporciona valores de plataforma de destino que se usan por el [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
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
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|CORDB_PLATFORM_WINDOWS_X86|La plataforma de destino es Windows ejecutándose en hardware Intel x86.|  
|CORDB_PLATFORM_WINDOWS_AMD64|La plataforma de destino es Windows de 64 bits ejecutándose en hardware AMD64 o Intel EM64T.|  
|CORDB_PLATFORM_WINDOWS_IA64|La plataforma de destino es Windows de 32 bits ejecutándose en hardware IA-64.|  
|CORDB_PLATFORM_MAC_PPC|La plataforma de destino es el sistema operativo Macintosh que se ejecuta en hardware PowerPC.|  
|CORDB_PLATFORM_MAC_X86|La plataforma de destino es el sistema operativo Macintosh ejecutándose en hardware Intel x86.|  
|CORDB_PLATFORM_WINDOWS_ARM|La plataforma de destino es el sistema operativo Macintosh que se ejecutan en hardware Windows ARM.|  
|CORDB_PLATFORM_MAC_AMD64|La plataforma de destino es el sistema operativo Macintosh ejecutándose en hardware AMD64.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
 Los miembros `CORDB_PLATFORM_WINDOWS_ARM` y `CORDB_PLATFORM_MAC_AMD64` están disponible en .NET Framework 4.5.2 y versiones posteriores.  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
