---
title: ICLRDebugging (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
ms.openlocfilehash: 9a768535c3bf69b5127777de4cee27054943091d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793640"
---
# <a name="iclrdebugging-interface"></a>ICLRDebugging (Interfaz)
Proporciona métodos que controlan la carga y descarga de módulos para depuración.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[OpenVirtualProcess (método)](iclrdebugging-openvirtualprocess-method.md)|Obtiene la interfaz "ICorDebugProcess" que corresponde a un módulo de Common Language Runtime (CLR) cargado en el proceso.|  
|[CanUnloadNow (método)](iclrdebugging-canunloadnow-method.md)|Determina si una biblioteca proporcionada por una interfaz [ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md) todavía está en uso o se puede descargar.|  
  
## <a name="remarks"></a>Notas  
 Puede obtener una instancia de la interfaz `ICLRDebugging` mediante la función [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) .  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
