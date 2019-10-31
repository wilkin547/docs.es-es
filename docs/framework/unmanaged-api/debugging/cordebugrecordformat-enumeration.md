---
title: Enumeración CorDebugRecordFormat
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
ms.openlocfilehash: 239b1a9f258f435e6dcca6e00cc20df5b5c01188
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097455"
---
# <a name="cordebugrecordformat-enumeration"></a>Enumeración CorDebugRecordFormat
Describe el formato de los datos de una matriz de bytes que contiene información sobre un evento de depuración de excepción nativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|Los datos son un registro de excepciones de Windows de 32 bits.|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|Los datos son un registro de excepciones de Windows de 64 bits.|  
  
## <a name="remarks"></a>Comentarios  
 Un miembro de la enumeración `CorDebugRecordFormat` se pasa al método [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) para indicar el formato de la matriz de bytes en su argumento `pRecord`.  
  
> [!NOTE]
> Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
