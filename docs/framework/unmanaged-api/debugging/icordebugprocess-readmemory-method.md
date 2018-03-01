---
title: "ICorDebugProcess::ReadMemory (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2d282e83fc7b7632bde850ac1341eef938d8e0dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parámetros  
 `address`  
 [in] Un `CORDB_ADDRESS` valor que especifica la dirección base de la memoria que se va a leer.  
  
 `size`  
 [in] El número de bytes que se leen de la memoria.  
  
 `buffer`  
 [out] Un búfer que recibe el contenido de la memoria.  
  
 `read`  
 [out] Un puntero al número de bytes transferidos en el búfer especificado.  
  
## <a name="remarks"></a>Comentarios  
 El `ReadMemory` método está pensado principalmente para usarse mediante la depuración de interoperabilidad para inspeccionar áreas de memoria que están siendo utilizados por la parte no administrada del código depurado. Este método también puede usarse para leer el código de lenguaje intermedio (MSIL) de Microsoft y el código nativo compilado JIT.  
  
 Los puntos de interrupción administrados se quitarán de los datos que se devuelven en el `buffer` parámetro. Para establezcan puntos de interrupción nativo, no se realizará ajustes [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 No se realiza ningún almacenamiento en caché de memoria de proceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
