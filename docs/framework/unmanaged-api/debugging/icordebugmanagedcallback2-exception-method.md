---
title: ICorDebugManagedCallback2::Exception (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
ms.openlocfilehash: e7125d923fb1d3757bb4ca53f5a7db806b241dd9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781526"
---
# <a name="icordebugmanagedcallback2exception-method"></a>ICorDebugManagedCallback2::Exception (Método)
Notifica al depurador que se ha iniciado una búsqueda de un controlador de excepciones.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pAppDomain`  
 de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso en el que se produjo la excepción.  
  
 `pThread`  
 de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.  
  
 `pFrame`  
 de Un puntero a un objeto ICorDebugFrame que representa un marco, determinado por el parámetro `dwEventType`. Para obtener más información, vea la tabla de la sección Comentarios.  
  
 `nOffset`  
 de Un entero que especifica un desplazamiento, según lo determinado por el parámetro `dwEventType`. Para obtener más información, vea la tabla de la sección Comentarios.  
  
 `dwEventType`  
 de Valor de la enumeración Cordebugexceptioncallbacktype (que especifica el tipo de esta devolución de llamada de excepción.  
  
 `dwFlags`  
 de Un valor de la enumeración [cordebugexceptionflags (](cordebugexceptionflags-enumeration.md) que especifica información adicional sobre la excepción.  
  
## <a name="remarks"></a>Notas  
 La devolución de llamada de `Exception` se llama en varios puntos durante la fase de búsqueda del proceso de control de excepciones. Es decir, se puede llamar más de una vez al desenredar una excepción.  
  
 La excepción que se está procesando se puede recuperar desde el objeto ICorDebugThread al que hace referencia el parámetro `pThread`.  
  
 El determinado marco y desplazamiento vienen determinados por el parámetro `dwEventType` como se indica a continuación:  
  
|Valor de `dwEventType`|Valor de `pFrame`|Valor de `nOffset`|  
|----------------------------|-----------------------|------------------------|  
|DEBUG_EXCEPTION_FIRST_CHANCE|Marco que produjo la excepción.|Puntero de instrucción en el marco.|  
|DEBUG_EXCEPTION_USER_FIRST_CHANCE|Marco de código de usuario más cercano al punto de la excepción iniciada.|Puntero de instrucción en el marco.|  
|DEBUG_EXCEPTION_CATCH_HANDLER_FOUND|Marco que contiene el controlador Catch.|Desplazamiento del lenguaje intermedio de Microsoft (MSIL) del principio del controlador Catch.|  
|DEBUG_EXCEPTION_UNHANDLED|NULL|Indefinido.|  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback2 (interfaz)](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback (interfaz)](icordebugmanagedcallback-interface.md)
