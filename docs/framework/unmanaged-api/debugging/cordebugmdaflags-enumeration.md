---
title: CorDebugMDAFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
ms.openlocfilehash: 34a66a8afa118ecaaaeea0b7b78daaadf1da7509
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778258"
---
# <a name="cordebugmdaflags-enumeration"></a>CorDebugMDAFlags (Enumeración)
Especifica el estado del subproceso en el que se activa el asistente para la depuración administrada (MDA).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|El subproceso en el que se ha desencadenado el MDA se ha retrasado desde que se activó el MDA.|  
  
## <a name="remarks"></a>Notas  
 Cuando la pila de llamadas ya no describe dónde se generó originalmente el MDA, se considera que el subproceso se ha *retrasado*. Se trata de una circunstancia inusual realizada por la ejecución del subproceso de una operación no válida al salir.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
