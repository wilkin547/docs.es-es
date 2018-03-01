---
title: "ICLRMetaHost::RequestRuntimeLoadedNotification (Método)"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b7866270d8c9234a375401dfd05b504a06ddbf4b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>ICLRMetaHost::RequestRuntimeLoadedNotification (Método)
Proporciona una función de devolución de llamada que se garantiza que se llama cuando una versión de common language runtime (CLR) se carga por primera vez, pero aún no se ha iniciado. Este método reemplaza a la [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
#### <a name="parameters"></a>Parámetros  
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
  
-   La devolución de llamada se invoca cuando un tiempo de ejecución se carga por primera vez.  
  
-   No se invoca la devolución de llamada para las cargas reentrantes del mismo runtime.  
  
-   Para las cargas en tiempo de ejecución no reentrante, llamadas a la función de devolución de llamada se serializan.  
  
 La función de devolución de llamada tiene el prototipo siguiente:  
  
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
  
 Si el host intenta cargar o producir otro tiempo de ejecución debe cargarse de manera reentrante, la `pfnCallbackThreadSet` y `pfnCallbackThreadUnset` parámetros que se proporcionan en la devolución de llamada de función debe usarse de la manera siguiente:  
  
-   `pfnCallbackThreadSet`debe llamarse desde el subproceso que podría provocar una carga en tiempo de ejecución antes de que se intenta realizar una carga de este tipo.  
  
-   `pfnCallbackThreadUnset`se debe llamar cuando el subproceso ya no hará que estos una carga en tiempo de ejecución (y antes de volver de la devolución de llamada inicial).  
  
-   `pfnCallbackThreadSet`y `pfnCallbackThreadUnset` son no reentrante.  
  
> [!NOTE]
>  Hospedar aplicaciones no deben llamar a `pfnCallbackThreadSet` y `pfnCallbackThreadUnset` fuera del ámbito de la `pCallbackFunction` parámetro.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRMetaHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
