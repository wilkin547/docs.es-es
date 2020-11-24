---
title: ICorDebugManagedCallback::LoadModule (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
ms.openlocfilehash: 698a5cb88884febc4dfb3b916c00df20c1a77819
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679655"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a>ICorDebugManagedCallback::LoadModule (Método)

Notifica al depurador que un módulo de Common Language Runtime (CLR) se ha cargado correctamente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pAppDomain`  
 de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se ha cargado el módulo.  
  
 `pModule`  
 de Un puntero a un objeto ICorDebugModule que representa el módulo CLR.  
  
## <a name="remarks"></a>Comentarios  

 La `LoadModule` devolución de llamada proporciona un tiempo adecuado para examinar los metadatos del módulo, establecer las marcas de compilador Just-in-Time (JIT) o habilitar o deshabilitar las devoluciones de llamada de carga de clases para el módulo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método UnloadModule](icordebugmanagedcallback-unloadmodule-method.md)
- [ICorDebugManagedCallback (Interfaz)](icordebugmanagedcallback-interface.md)
