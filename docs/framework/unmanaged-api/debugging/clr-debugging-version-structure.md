---
title: CLR_DEBUGGING_VERSION (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLR_DEBUGGING_VERSION
api_location: mscordbi.dll
api_type: COM
f1_keywords: CLR_DEBUGGING_VERSION
helpviewer_keywords: CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 98124b7b9efb2c92ebee6b6e99f73edc6cf173a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="clrdebuggingversion-structure"></a>CLR_DEBUGGING_VERSION (Estructura)
Define la versión de producto de Common Language Runtime (CLR) con fines de depuración.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Typedef struct _CLR_DEBUGGING_VERSION  
{  
WORD wStructVersion;  
WORD wMajor;   
WORD wMinor;  
WORD wBuild;  
WORD wRevision;  
}  CLR_DEBUGGING_VERSION;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`wStructVersion`|El número de versión de estructura|  
|`wMajor`|Número de versión principal.|  
|`wMinor`|Número de versión secundaria.|  
|`wBuild`|El número de compilación.|  
|`wRevision`|El número de revisión.|  
  
## <a name="remarks"></a>Comentarios  
 El `CLR_DEBUGGING_VERSION` estructura es el mismo que el COR_VERSION (estructura), sin embargo, el `CLR_DEBUGGING_VERSION` estructura proporciona un campo de versión de una estructura adicional (`wStructVersion`). Actualmente, este campo debe establecerse en cero.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
