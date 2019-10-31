---
title: StackOverflowInfo (Estructura)
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: 1072026f92edbc646653c6dd74ec8e22d5b887e5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105919"
---
# <a name="stackoverflowinfo-structure"></a>StackOverflowInfo (Estructura)
Almacena el tipo de desbordamiento que se ha producido y la información sobre la excepción que se produjo debido al desbordamiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`soType`|Valor de la enumeración [StackOverflowType (](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) que especifica el tipo de desbordamiento.|  
|`pExceptionInfo`|Un puntero a un objeto de `EXCEPTION_POINTERS` de Win32, que contiene un registro de excepción con una descripción independiente del equipo de una excepción y un registro de contexto con una descripción dependiente del equipo del contexto del procesador en el momento de la excepción.|  
  
## <a name="remarks"></a>Comentarios  
 Se pasa un objeto `StackOverflowInfo` al método [IActionOnCLREvent:: onEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) para eventos de `Event_StackOverflow`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. idl  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
