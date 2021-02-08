---
description: 'Más información acerca de: estructura Coreclrdebugprocinfo ('
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
ms.openlocfilehash: 04befb057be689e68dd3571a13990da9af64551f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801493"
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
  
|Miembro|Descripción|  
|------------|-----------------|  
|`m_dwPID`|Identificador del proceso asignado por el sistema operativo.|  
|`m_dwInternalID`|Identificador del proceso asignado por el proxy de depuración remota que se ejecuta en el equipo de destino. Este identificador se recicla con menos frecuencia que el identificador del sistema operativo.|  
|`m_wszName`|Línea de comandos del proceso. Este miembro puede truncarse.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Biblioteca:** mscordbi_macx86.dll  
  
 **.NET Framework versiones:** 3,5 SP1
