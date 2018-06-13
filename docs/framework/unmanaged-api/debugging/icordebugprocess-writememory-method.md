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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6da4c282c7f969a406a657d1e30dd6120a32b4e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420913"
---
# <a name="icordebugprocesswritememory-method"></a>ICorDebugProcess::WriteMemory (Método)
Escribe datos en un área de memoria en este proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `address`  
 [in] Un `CORDB_ADDRESS` valor que es la dirección base del área de memoria para los datos que se escribe. Antes de que ocurra la transferencia de datos, el sistema comprueba que el área de memoria del tamaño especificado, empezando por la dirección base es accesible para escribir en él. Si no está accesible, se produce un error en el método.  
  
 `size`  
 [in] El número de bytes que se escribirán en el área de memoria.  
  
 `buffer`  
 [in] Un búfer que contiene datos que se va a escribir.  
  
 `written`  
 [out] Un puntero a una variable que recibe el número de bytes escritos en el área de memoria en este proceso. Si `written` es NULL, este parámetro se ignora.  
  
## <a name="remarks"></a>Comentarios  
 Datos se escriben automáticamente detrás de los puntos de interrupción. En la versión 2.0 de .NET Framework, los depuradores nativos no deben usar este método para insertar puntos de interrupción en la secuencia de instrucciones. Use [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) en su lugar.  
  
 El `WriteMemory` método debe utilizarse solo fuera del código administrado. Este método puede dañar el tiempo de ejecución si se utiliza incorrectamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
