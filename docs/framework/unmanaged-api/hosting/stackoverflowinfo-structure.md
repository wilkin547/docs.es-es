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
ms.openlocfilehash: 941093b9a0856c2b716ba359c854473f3c9ea26a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006524"
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
|`soType`|Valor de la enumeración [StackOverflowType (](stackoverflowtype-enumeration.md) que especifica el tipo de desbordamiento.|  
|`pExceptionInfo`|Un puntero a un `EXCEPTION_POINTERS` objeto Win32, que contiene un registro de excepción con una descripción independiente de la máquina de una excepción y un registro de contexto con una descripción dependiente del equipo del contexto del procesador en el momento de la excepción.|  
  
## <a name="remarks"></a>Comentarios  
 Un `StackOverflowInfo` objeto se pasa al método [IActionOnCLREvent:: onEvent](iactiononclrevent-onevent-method.md) para `Event_StackOverflow` los eventos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. idl  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de hospedaje](hosting-structures.md)
