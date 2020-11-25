---
title: Método ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 41385fe915733f052af67c82d984c8b9d853c579
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713826"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a>Método ICorDebugDataTarget2::GetImageFromPointer

Devuelve el tamaño y dirección base del módulo a partir de una dirección de ese módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `addr`  
 [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) valor que representa una dirección de un módulo.  
  
 `pImageBase`  
 enuncia [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) valor que representa la dirección base del módulo.  
  
 `pSize`  
 Puntero al tamaño del módulo.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
