---
title: CLR_DEBUGGING_VERSION (Estructura)
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4049b0ed25d4c0fda00fe9b0dad5887fa4f6996
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506945"
---
# <a name="clrdebuggingversion-structure"></a>CLR_DEBUGGING_VERSION (Estructura)
Define la versión de producto de Common Language Runtime (CLR) con fines de depuración.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`wStructVersion`|El número de versión de la estructura|  
|`wMajor`|Número de versión principal.|  
|`wMinor`|Número de versión secundaria.|  
|`wBuild`|El número de compilación.|  
|`wRevision`|El número de revisión.|  
  
## <a name="remarks"></a>Comentarios  
 El `CLR_DEBUGGING_VERSION` estructura es igual que el COR_VERSION (estructura), sin embargo, el `CLR_DEBUGGING_VERSION` estructura proporciona un campo de versión de una estructura adicional (`wStructVersion`). Actualmente, este campo debe establecerse en cero.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
