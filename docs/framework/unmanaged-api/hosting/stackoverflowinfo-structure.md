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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac0f5d522a24394369583692f8c564254529bf13
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137356"
---
# <a name="stackoverflowinfo-structure"></a>StackOverflowInfo (Estructura)
Almacena el tipo de desbordamiento que se ha producido e información sobre la excepción que se produjo debido a desbordamiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`soType`|Un valor de la [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeración que especifica el tipo de desbordamiento.|  
|`pExceptionInfo`|Un puntero a Win32 `EXCEPTION_POINTERS` objeto, que contiene un registro de excepciones con una descripción independiente del equipo de una excepción y un registro de contexto con una descripción de la máquina dependiente del contexto del procesador en el momento de la excepción.|  
  
## <a name="remarks"></a>Comentarios  
 Un `StackOverflowInfo` objeto se pasa a la [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) método para `Event_StackOverflow` eventos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.idl  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
