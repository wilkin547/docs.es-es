---
title: Método ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 31a839076b34901ae1a8f3b43021f64f77629fc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713852"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a>Método ICorDebugDataTarget2::EnumerateThreadIDs

Devuelve una lista de identificadores de subprocesos activos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 cThreadIDs  
 [in] Número máximo de subprocesos cuyos identificadores se pueden devolver.  
  
 pcThreadIds  
 [out] Puntero a un `ULONG32` que indica el número real de identificadores de subproceso escritos en la matriz `pThreadIds`.  
  
 pThreadIDs  
 Matriz de identificadores de subproceso.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Consulte [requisitos del sistema](../../get-started/system-requirements.md). **Encabezado:** Cordebug. idl, Cordebug. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
