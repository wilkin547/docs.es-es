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
ms.openlocfilehash: 30ec8cc8bbbd6d49f89cd67371c3326c0cb0df9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680617"
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
 de Máscara de valores de acceso que especifican los tipos de acceso solicitados al token de subproceso. Estos valores se definen en la función de Win32 `OpenThreadToken` . Los tipos de acceso solicitados se concilian con la lista de control de acceso discrecional (DACL) del token para determinar qué tipos de acceso se conceden o deniegan.  
  
 `bOpenAsSelf`  
 [in] `true` para especificar que la comprobación de acceso se debe realizar utilizando el contexto de seguridad del proceso para el subproceso que realiza la llamada; `false` para especificar que la comprobación de acceso debe realizarse mediante el contexto de seguridad para el propio subproceso que realiza la llamada. Si el subproceso está suplantando a un cliente, el contexto de seguridad puede ser el de un proceso de cliente.  
  
 `phThreadToken`  
 enuncia Puntero al token de acceso que se acaba de abrir.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  

 `IHostSecurityManager::OpenThreadToken` se comporta de forma similar a la función de Win32 correspondiente del mismo nombre, salvo que la función de Win32 permite que el llamador pase un identificador a un subproceso arbitrario, mientras que `IHostSecurityManager::OpenThreadToken` solo abre el token asociado al subproceso que realiza la llamada.  
  
 El `HANDLE` tipo no es compatible con com, es decir, su tamaño es específico del sistema operativo y requiere serialización personalizada. Por lo tanto, este token solo se usa en el proceso, entre el CLR y el host.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IHostSecurityContext (Interfaz)](ihostsecuritycontext-interface.md)
- [IHostSecurityManager (Interfaz)](ihostsecuritymanager-interface.md)
