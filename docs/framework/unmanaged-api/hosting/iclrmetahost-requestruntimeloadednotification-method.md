---
title: ICLRMetaHost::RequestRuntimeLoadedNotification (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61fce3e06b5245872f7061716e8d995dd5f5043c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224889"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>ICLRMetaHost::RequestRuntimeLoadedNotification (Método)
Proporciona una función de devolución de llamada que se garantiza que se llama cuando una versión de common language runtime (CLR) se carga por primera vez, pero aún no se ha iniciado. Este método reemplaza el [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pCallbackFunction`  
 [in] La función de devolución de llamada que se invoca cuando se ha cargado un nuevo tiempo de ejecución.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`pCallbackFunction` es null.|  
  
## <a name="remarks"></a>Comentarios  
 La devolución de llamada funciona de la manera siguiente:  
  
-   La devolución de llamada se invoca sólo cuando se carga un tiempo de ejecución por primera vez.  
  
-   No se invoca la devolución de llamada para las cargas reentrantes del mismo runtime.  
  
-   Para las cargas no reentrante en tiempo de ejecución, se serializan las llamadas a la función de devolución de llamada.  
  
 La función de devolución de llamada tiene el siguiente prototipo:  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 Los prototipos de función de devolución de llamada son los siguientes:  
  
-   `pfnCallbackThreadSet`:  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
-   `pfnCallbackThreadUnset`:  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 Si el host intenta cargar o producir otro tiempo de ejecución que se cargue en un modo reentrante, la `pfnCallbackThreadSet` y `pfnCallbackThreadUnset` parámetros que se proporcionan en la devolución de llamada de función debe usarse en la siguiente manera:  
  
-   `pfnCallbackThreadSet` debe llamarse por el subproceso que podría causar una carga en tiempo de ejecución antes de intenta una carga de este tipo.  
  
-   `pfnCallbackThreadUnset` se debe llamar cuando el subproceso ya no hará que la carga de tiempo de ejecución (y antes de abandonar la devolución de llamada inicial).  
  
-   `pfnCallbackThreadSet` y `pfnCallbackThreadUnset` son ambos no reentrante.  
  
> [!NOTE]
>  No deben llamar las aplicaciones host `pfnCallbackThreadSet` y `pfnCallbackThreadUnset` fuera del ámbito de la `pCallbackFunction` parámetro.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MetaHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRMetaHost (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md)
