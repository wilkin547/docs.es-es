---
description: 'Más información acerca de: ICorDebugMemoryBuffer:: método de método'
title: ICorDebugMemoryBuffer::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 7de23dd13a1e0ef841145e3845d7d0052ce3ef9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754045"
---
# <a name="icordebugmemorybuffergetsize-method"></a>ICorDebugMemoryBuffer::GetSize (método)

Obtiene el tamaño del búfer de memoria en bytes.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pcbBufferLength`  
 [out] Puntero al tamaño del búfer de memoria.  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
