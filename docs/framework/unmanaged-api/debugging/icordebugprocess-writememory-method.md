---
title: ICorDebugProcess::WriteMemory (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
ms.openlocfilehash: 0a433ccb81ef62ac92a4553a838a2c98a04fc7c1
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212820"
---
# <a name="icordebugprocesswritememory-method"></a>ICorDebugProcess::WriteMemory (Método)
Escribe datos en un área de memoria de este proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a>Parámetros  
 `address`  
 de Un `CORDB_ADDRESS` valor que es la dirección base del área de memoria en la que se escriben los datos. Antes de que se produzca la transferencia de datos, el sistema comprueba que el área de memoria del tamaño especificado, a partir de la dirección base, es accesible para escritura. Si no es accesible, se produce un error en el método.  
  
 `size`  
 de Número de bytes que se van a escribir en el área de memoria.  
  
 `buffer`  
 de Búfer que contiene los datos que se van a escribir.  
  
 `written`  
 enuncia Puntero a una variable que recibe el número de bytes escritos en el área de memoria de este proceso. Si `written` es null, se omite este parámetro.  
  
## <a name="remarks"></a>Observaciones  
 Los datos se escriben automáticamente detrás de los puntos de interrupción. En la versión .NET Framework 2,0, los depuradores nativos no deben usar este método para insertar puntos de interrupción en la secuencia de instrucciones. Use [ICorDebugProcess2:: SetUnmanagedBreakpoint (](icordebugprocess2-setunmanagedbreakpoint-method.md) en su lugar.  
  
 El `WriteMemory` método solo se debe usar fuera del código administrado. Este método puede dañar el tiempo de ejecución si se usa de forma incorrecta.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
