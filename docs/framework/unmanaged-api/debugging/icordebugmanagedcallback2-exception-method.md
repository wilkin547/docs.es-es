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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8952b34781045089945e7e72e179e88300b5fdd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103355"
---
# <a name="icordebugmanagedcallback2exception-method"></a>ICorDebugManagedCallback2::Exception (Método)
Notifica al depurador que se ha iniciado una búsqueda de un controlador de excepciones.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pAppDomain`  
 [in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso en el que se produjo la excepción.  
  
 `pThread`  
 [in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.  
  
 `pFrame`  
 [in] Un puntero a un objeto ICorDebugFrame que representa un marco, según lo determinado por la `dwEventType` parámetro. Para obtener más información, vea la tabla en la sección Comentarios.  
  
 `nOffset`  
 [in] Un entero que especifica un desplazamiento, según lo determinado por la `dwEventType` parámetro. Para obtener más información, vea la tabla en la sección Comentarios.  
  
 `dwEventType`  
 [in] Un valor de la enumeración CorDebugExceptionCallbackType que especifica el tipo de devolución de llamada de esta excepción.  
  
 `dwFlags`  
 [in] Un valor de la [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeración que especifica información adicional sobre la excepción  
  
## <a name="remarks"></a>Comentarios  
 El `Exception` devolución de llamada se llama en varios puntos durante la fase de búsqueda del proceso de control de excepciones. Es decir, puede llamar más de una vez mientras desenredar una excepción.  
  
 La excepción que se está procesando se puede recuperar desde el objeto ICorDebugThread al que hace referencia el `pThread` parámetro.  
  
 El marco determinado y el desplazamiento se determinan por la `dwEventType` parámetro como sigue:  
  
|Valor de `dwEventType`|Valor de `pFrame`|Valor de `nOffset`|  
|----------------------------|-----------------------|------------------------|  
|DEBUG_EXCEPTION_FIRST_CHANCE|El marco que produjo la excepción.|El puntero de instrucción en el marco.|  
|DEBUG_EXCEPTION_USER_FIRST_CHANCE|El marco de código de usuario más cercano al punto de la excepción generada.|El puntero de instrucción en el marco.|  
|DEBUG_EXCEPTION_CATCH_HANDLER_FOUND|El marco que contiene el controlador catch.|El desplazamiento de lenguaje intermedio (MSIL) de Microsoft del principio de que el controlador catch.|  
|DEBUG_EXCEPTION_UNHANDLED|NULL|Sin definir.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
