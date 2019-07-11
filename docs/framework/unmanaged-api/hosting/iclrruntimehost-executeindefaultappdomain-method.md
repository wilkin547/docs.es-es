---
title: ICLRRuntimeHost::ExecuteInDefaultAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b7540f166311bbc9e5efa21d136132cc72b7c12
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768739"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a>ICLRRuntimeHost::ExecuteInDefaultAppDomain (Método)
Llama al método especificado del tipo especificado en el ensamblado administrado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzAssemblyPath`  
 [in] La ruta de acceso a la <xref:System.Reflection.Assembly> que define el <xref:System.Type> cuyo método es que se debe invocar.  
  
 `pwzTypeName`  
 [in] El nombre de la <xref:System.Type> que define el método que se invoca.  
  
 `pwzMethodName`  
 [in] El nombre del método que se va a invocar.  
  
 `pwzArgument`  
 [in] El parámetro de cadena para pasar al método.  
  
 `pReturnValue`  
 [out] El valor entero devuelto por el método invocado.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|DESCRIPCIÓN|  
|-------------|-----------------|  
|S_OK|`ExecuteInDefaultAppDomain` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Si el método devuelve E_FAIL, ya no es utilizable dentro del proceso de la CRL. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El método invocado debe tener la siguiente firma:  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 donde `pwzMethodName` representa el nombre del método invocado, y `pwzArgument` representa el valor de cadena se pasa como parámetro a ese método. Si se establece el valor HRESULT a S_OK, `pReturnValue` se establece en el valor entero devuelto por el método invocado. En caso contrario, `pReturnValue` no está establecida.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
