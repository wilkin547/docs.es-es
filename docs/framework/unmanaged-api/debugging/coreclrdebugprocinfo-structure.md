---
title: CoreClrDebugProcInfo (Estructura)
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21fc34add4038d25d60e4728847e0d84914a14e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739415"
---
# <a name="coreclrdebugprocinfo-structure"></a>CoreClrDebugProcInfo (Estructura)
Representa un proceso que se ejecuta en un equipo remoto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`m_dwPID`|Identificador del proceso asignado por el sistema operativo.|  
|`m_dwInternalID`|Identificador del proceso asignado por el proxy de depuración remota que se ejecuta en el equipo de destino. Este identificador se recicla con menos frecuencia que el identificador del sistema operativo.|  
|`m_wszName`|Línea de comandos del proceso. Este miembro puede truncarse.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CoreClrRemoteDebuggingInterfaces.h  
  
 **Library:** mscordbi_macx86.dll  
  
 **Versiones de .NET framework:** 3.5 SP1
