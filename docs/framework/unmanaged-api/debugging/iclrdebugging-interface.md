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
ms.openlocfilehash: 6eea7f6c222b8e30376ec72ee0c193a68c23f0d0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723563"
---
# <a name="iclrdebugging-interface"></a>ICLRDebugging (Interfaz)

Proporciona métodos que controlan la carga y descarga de módulos para depuración.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md)|Obtiene la interfaz "ICorDebugProcess" que corresponde a un módulo de Common Language Runtime (CLR) cargado en el proceso.|  
|[Método CanUnloadNow](iclrdebugging-canunloadnow-method.md)|Determina si una biblioteca proporcionada por una interfaz [ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md) todavía está en uso o se puede descargar.|  
  
## <a name="remarks"></a>Comentarios  

 Puede obtener una instancia de la `ICLRDebugging` interfaz mediante la función [CLRCreateInstance](../hosting/clrcreateinstance-function.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
