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
ms.openlocfilehash: b9d4b27ca0bf454b42f15b849008e5a3019bb09a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864083"
---
# <a name="coreclrdebugprocinfo-structure"></a>CoreClrDebugProcInfo (Estructura)
Representa un proceso que se ejecuta en un equipo remoto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`m_dwPID`|Identificador del proceso asignado por el sistema operativo.|  
|`m_dwInternalID`|Identificador del proceso asignado por el proxy de depuración remota que se ejecuta en el equipo de destino. Este identificador se recicla con menos frecuencia que el identificador del sistema operativo.|  
|`m_wszName`|Línea de comandos del proceso. Este miembro puede truncarse.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CoreClrRemoteDebuggingInterfaces.h  
  
 **Library:** mscordbi_macx86.dll  
  
 **Versiones de .NET framework:** 3.5 SP1
