---
title: ICorDebugHeapValue3::GetMonitorEventWaitList (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetMonitorEventWaitList
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList
helpviewer_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList method [.NET Framework debugging]
- GetMonitorEventWaitList method [.NET Framework debugging]
ms.assetid: 035a9035-ac66-4953-b48a-99652b42b7fe
topic_type:
- apiref
ms.openlocfilehash: 21bf0122039a720ff8a1d38d62e77c2560dcc435
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726540"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a>ICorDebugHeapValue3::GetMonitorEventWaitList (Método)

Proporciona una lista ordenada de subprocesos que se ponen en cola en el evento que está asociado a un bloqueo de monitor.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppThreadEnum`  
 enuncia El enumerador ICorDebugThreadEnum (que proporciona la lista ordenada de subprocesos.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La lista no está vacía.|  
|S_FALSE|La lista está vacía.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Notas  

 El primer subproceso de la lista es el primer subproceso publicado por la siguiente llamada a <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType> . El siguiente subproceso de la lista se libera en la llamada siguiente, y así sucesivamente.  
  
 Si la lista no está vacía, este método devuelve S_OK. Si la lista está vacía, el método devuelve S_FALSE; en este caso, la enumeración sigue siendo válida, aunque está vacía.  
  
 En cualquier caso, la interfaz de enumeración solo se puede usar para la duración del estado sincronizado actual. Sin embargo, las interfaces del subproceso dispensadas de él son válidas hasta que se cierra el subproceso.  
  
 Si `ppThreadEnum` no es un puntero válido, el resultado es indefinido.  
  
 Si se produce un error de modo que no se pueda determinar qué subprocesos están esperando, si hay alguno, el monitor, el método devuelve un valor HRESULT que indica un error.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
