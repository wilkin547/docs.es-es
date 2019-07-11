---
title: CoreClrDebugRuntimeInfo (Estructura)
ms.date: 03/30/2017
api_name:
- CoreClrDebugRuntimeInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugRuntimeInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreDebugRuntimeInfo structure
- Silverlight, remote debugging
ms.assetid: bd01c30f-b7a8-4179-9497-622b6599b1a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b58832e110f67a54d3bd57a7284b2e26e43d6bf7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739407"
---
# <a name="coreclrdebugruntimeinfo-structure"></a>CoreClrDebugRuntimeInfo (Estructura)
Representa una instancia de Common Language Runtime (CLR) que se carga en un proceso en un equipo remoto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`m_dwInternalID`|Identificador en tiempo de ejecución asignado por el proxy de depuración remota en ejecución en el equipo de destino.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CoreClrRemoteDebuggingInterfaces.h  
  
 **Library:** mscordbi_macx86.dll  
  
 **Versiones de .NET framework:** 3.5 SP1
