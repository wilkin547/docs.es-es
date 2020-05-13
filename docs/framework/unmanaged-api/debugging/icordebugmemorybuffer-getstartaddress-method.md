---
title: ICorDebugMemoryBuffer::GetStartAddress (método)
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: 47369c744ee42fb03857a3e69063a04e4f509d0d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212352"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a>ICorDebugMemoryBuffer::GetStartAddress (método)
Obtiene la dirección de inicio del búfer de memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `address`  
 [out] Puntero a la dirección de inicio del búfer de memoria.  
  
## <a name="remarks"></a>Observaciones  
  
> [!WARNING]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
