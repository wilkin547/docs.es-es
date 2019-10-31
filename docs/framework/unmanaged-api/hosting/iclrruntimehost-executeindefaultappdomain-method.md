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
ms.openlocfilehash: ed841d1b2ff346ebef668cbd96a58ddfe466b3b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120444"
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
 de Ruta de acceso al <xref:System.Reflection.Assembly> que define el <xref:System.Type> cuyo método se va a invocar.  
  
 `pwzTypeName`  
 de Nombre del <xref:System.Type> que define el método que se va a invocar.  
  
 `pwzMethodName`  
 de Nombre del método que se va a invocar.  
  
 `pwzArgument`  
 de Parámetro de cadena que se va a pasar al método.  
  
 `pReturnValue`  
 enuncia El valor entero devuelto por el método invocado.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`ExecuteInDefaultAppDomain` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Si un método devuelve E_FAIL, la CRL ya no se podrá usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El método invocado debe tener la siguiente firma:  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 donde `pwzMethodName` representa el nombre del método invocado y `pwzArgument` representa el valor de cadena que se pasa como parámetro a ese método. Si el valor HRESULT se establece en S_OK, `pReturnValue` se establece en el valor entero devuelto por el método invocado. De lo contrario, no se establece `pReturnValue`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
