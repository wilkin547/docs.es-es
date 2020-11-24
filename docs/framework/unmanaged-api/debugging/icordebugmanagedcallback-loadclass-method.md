---
title: ICorDebugManagedCallback::LoadClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
ms.openlocfilehash: 6f1672d40cd495d3ec099abc703639cf52460703
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679668"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a>ICorDebugManagedCallback::LoadClass (Método)

Notifica al depurador que se ha cargado una clase.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pAppDomain`  
 de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se ha cargado la clase.  
  
 `c`  
 de Un puntero a un objeto ICorDebugClass que representa la clase.  
  
## <a name="remarks"></a>Comentarios  

 Esta devolución de llamada solo se produce si se ha habilitado la carga de clases para el módulo que contiene la clase. La carga de clases está siempre habilitada para los módulos dinámicos.  
  
 La `LoadClass` devolución de llamada proporciona un tiempo adecuado para enlazar puntos de interrupción a clases recién generadas en módulos dinámicos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método UnloadClass](icordebugmanagedcallback-unloadclass-method.md)
- [ICorDebugManagedCallback (Interfaz)](icordebugmanagedcallback-interface.md)
