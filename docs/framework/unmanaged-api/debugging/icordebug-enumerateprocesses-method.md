---
title: ICorDebug::EnumerateProcesses (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.EnumerateProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type:
- apiref
ms.openlocfilehash: 09a8a2bb38378f5d4a32d7b00b68d02f1aa4c054
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110710"
---
# <a name="icordebugenumerateprocesses-method"></a>ICorDebug::EnumerateProcesses (Método)
Obtiene un enumerador para los procesos que se están depurando.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppProcess`  
 Puntero a la dirección de un objeto Icordebugprocessenum (que es el enumerador para los procesos que se están depurando.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
