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
ms.openlocfilehash: 40dbfc60f8bde1198fd56a4a8aeed1dd6879d1ae
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795630"
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
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`m_dwPID`|Identificador del proceso asignado por el sistema operativo.|  
|`m_dwInternalID`|Identificador del proceso asignado por el proxy de depuración remota que se ejecuta en el equipo de destino. Este identificador se recicla con menos frecuencia que el identificador del sistema operativo.|  
|`m_wszName`|Línea de comandos del proceso. Este miembro puede truncarse.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Biblioteca:** mscordbi_macx86. dll  
  
 **.NET Framework versiones:** 3,5 SP1
