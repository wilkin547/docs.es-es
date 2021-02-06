---
description: 'Más información sobre: enumeración CorDebugMDAFlags ('
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
ms.openlocfilehash: d7e9178d76286b112035729e997b1f68e2a93fb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661940"
---
# <a name="cordebugmdaflags-enumeration"></a>CorDebugMDAFlags (Enumeración)

Especifica el estado del subproceso en el que se activa el asistente para la depuración administrada (MDA).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|El subproceso en el que se ha desencadenado el MDA se ha retrasado desde que se activó el MDA.|  
  
## <a name="remarks"></a>Observaciones  

 Cuando la pila de llamadas ya no describe dónde se generó originalmente el MDA, se considera que el subproceso se ha *retrasado*. Se trata de una circunstancia inusual realizada por la ejecución del subproceso de una operación no válida al salir.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
