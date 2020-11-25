---
title: ICorDebugProcess::ReadMemory (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
ms.openlocfilehash: a0abc7168ff7bffdbb835c1c1bc93de9df6e381c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694872"
---
# <a name="icordebugprocessreadmemory-method"></a>ICorDebugProcess::ReadMemory (Método)

Lee un área especificada de memoria para este proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a>Parámetros  

 `address`  
 de `CORDB_ADDRESS` Valor que especifica la dirección base de la memoria que se va a leer.  
  
 `size`  
 de Número de bytes que se van a leer de la memoria.  
  
 `buffer`  
 enuncia Búfer que recibe el contenido de la memoria.  
  
 `read`  
 enuncia Puntero al número de bytes transferidos al búfer especificado.  
  
## <a name="remarks"></a>Comentarios  

 El `ReadMemory` método está pensado principalmente para que lo use la depuración de interoperabilidad para inspeccionar las regiones de memoria que usa la parte no administrada del código que se está depurando. Este método también se puede usar para leer el código del lenguaje intermedio de Microsoft (MSIL) y el código compilado JIT nativo.  
  
 Los puntos de interrupción administrados se quitarán de los datos que se devuelven en el `buffer` parámetro. No se realizarán ajustes para los puntos de interrupción nativos establecidos por [ICorDebugProcess2:: SetUnmanagedBreakpoint (](icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 No se realiza ningún almacenamiento en caché de la memoria del proceso.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
