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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 218279684304b766a9bf009f5891ac4910254a3c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492171"
---
# <a name="icordebugprocessreadmemory-method"></a>ICorDebugProcess::ReadMemory (Método)
Lee un área especificada de memoria para este proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a>Parámetros  
 `address`  
 [in] Un `CORDB_ADDRESS` valor que especifica la dirección base de la memoria que se va a leer.  
  
 `size`  
 [in] El número de bytes que se leen de la memoria.  
  
 `buffer`  
 [out] Un búfer que recibe el contenido de la memoria.  
  
 `read`  
 [out] Un puntero al número de bytes transferidos en el búfer especificado.  
  
## <a name="remarks"></a>Comentarios  
 El `ReadMemory` método está pensado principalmente para usarse mediante la depuración de interoperabilidad para inspeccionar las regiones de memoria que están siendo utilizadas por la parte del código depurado no administrada. Este método también puede utilizarse para leer el código de lenguaje intermedio (MSIL) de Microsoft y código nativo compilado JIT.  
  
 Ningún punto de interrupción administrado se quitarán los datos que se devuelven en el `buffer` parámetro. Para establecer puntos de interrupción nativos, no se realizará ningún ajuste [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 No se realiza ningún almacenamiento en caché de memoria de proceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
