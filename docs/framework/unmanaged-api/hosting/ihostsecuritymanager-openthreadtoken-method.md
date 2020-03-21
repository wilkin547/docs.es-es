---
title: IHostSecurityManager::OpenThreadToken (Método)
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
ms.openlocfilehash: 11d042ea9eecc8d428761da6eaa15f7c2907ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176271"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>IHostSecurityManager::OpenThreadToken (Método)
Abre el token de acceso discrecional asociado al subproceso que se está ejecutando actualmente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,
    [in]  BOOL     bOpenAsSelf,
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwDesiredAccess`  
 [en] Máscara de valores de acceso que especifican los tipos de acceso solicitados al token de subproceso. Estos valores se definen `OpenThreadToken` en la función Win32. Los tipos de acceso solicitados se reconcilian con la lista de control de acceso discrecional (DACL) del token para determinar qué tipos de acceso conceder o denegar.  
  
 `bOpenAsSelf`  
 [en] `true` para especificar que la comprobación de acceso debe realizarse mediante el contexto de seguridad del proceso para el subproceso que realiza la llamada; `false` para especificar que la comprobación de acceso se debe realizar mediante el contexto de seguridad para el propio subproceso que realiza la llamada. Si el subproceso está suplantando a un cliente, el contexto de seguridad puede ser el de un proceso de cliente.  
  
 `phThreadToken`  
 [fuera] Un puntero al token de acceso recién abierto.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken`regresó con éxito.|  
|HOST_E_CLRNOTAVAILABLE|Common Language Runtime (CLR) no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se adelantó la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no es el propietario de la cerradura.|  
|HOST_E_ABANDONED|Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.|  
|E_FAIL|Se ha producido un fallo catastrófico desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  
 `IHostSecurityManager::OpenThreadToken`se comporta de forma similar a la función Win32 correspondiente del mismo nombre, excepto que la función `IHostSecurityManager::OpenThreadToken` Win32 permite al autor de la llamada pasar un identificador a un subproceso arbitrario, mientras que abre solo el token asociado al subproceso que realiza la llamada.  
  
 El `HANDLE` tipo no es compatible con COM, es decir, su tamaño es específico del sistema operativo y requiere el cálculo de referencias personalizado. Por lo tanto, este token se usa solo dentro del proceso, entre CLR y el host.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MScorEE.h  
  
 **Biblioteca:** Incluido como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IHostSecurityContext (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [IHostSecurityManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
