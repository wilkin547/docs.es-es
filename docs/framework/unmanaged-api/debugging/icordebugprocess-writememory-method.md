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
ms.openlocfilehash: 2e9d640fb1c9dae5bb195baa504e560ba8e45821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930304"
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
  
## <a name="parameters"></a>Parámetros  
 `address`  
 [in] Un `CORDB_ADDRESS` valor que es la dirección base del área de memoria para los datos que se escribe. Antes de que se produce la transferencia de datos, el sistema comprueba que el área de memoria del tamaño especificado, comenzando en la dirección base, es accesible para escribir en él. Si no es accesible, el método produce un error.  
  
 `size`  
 [in] El número de bytes que se escriban en el área de memoria.  
  
 `buffer`  
 [in] Un búfer que contiene los datos se escriban.  
  
 `written`  
 [out] Un puntero a una variable que recibe el número de bytes escritos en el área de memoria en este proceso. Si `written` es NULL, se omite este parámetro.  
  
## <a name="remarks"></a>Comentarios  
 Automáticamente se escriben los datos detrás de cualquier punto de interrupción. En la versión 2.0 de .NET Framework, los depuradores nativos no deben usar este método para insertar puntos de interrupción en la secuencia de instrucciones. Use [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) en su lugar.  
  
 El `WriteMemory` método se debe usar sólo fuera del código administrado. Este método puede dañar el tiempo de ejecución si se utiliza incorrectamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
