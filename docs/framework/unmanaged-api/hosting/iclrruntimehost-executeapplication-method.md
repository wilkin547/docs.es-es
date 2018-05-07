---
title: ICLRRuntimeHost::ExecuteApplication (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56a49b3d08b58da109924267e6c23c188efefe29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="iclrruntimehostexecuteapplication-method"></a>ICLRRuntimeHost::ExecuteApplication (Método)
Se utiliza en escenarios de implementación de ClickOnce basada en manifiestos para especificar la aplicación que se debe activar en un nuevo dominio. Para obtener más información acerca de estos escenarios, vea [seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pwzAppFullName`  
 [in] El nombre completo de la aplicación, tal como se define para <xref:System.ApplicationIdentity>.  
  
 `dwManifestPaths`  
 [in] El número de cadenas incluidas en el `ppwzManifestPaths` matriz.  
  
 `ppwzManifestPaths`  
 [in] Opcional. Matriz de cadenas que contiene las rutas de acceso de manifiestos de la aplicación.  
  
 `dwActivationData`  
 [in] El número de cadenas incluidas en el `ppwzActivationData` matriz.  
  
 `ppwzActivationData`  
 [in] Opcional. Matriz de cadenas que contiene los datos de activación de la aplicación, como la parte de la cadena de consulta de la dirección URL para las aplicaciones implementadas a través de Internet.  
  
 `pReturnValue`  
 [out] El valor devuelto desde el punto de entrada de la aplicación.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`ExecuteApplication` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada agotó el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 `ExecuteApplication` se usa para activar aplicaciones ClickOnce en un dominio de aplicación recién creado.  
  
 El `pReturnValue` parámetro de salida se establece en el valor devuelto por la aplicación. Si proporciona un valor null para `pReturnValue`, `ExecuteApplication` no se producen errores, pero no devuelve un valor.  
  
> [!IMPORTANT]
>  No llame a la [método Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) método antes de llamar a la `ExecuteApplication` método para activar una aplicación basada en manifiestos. Si el `Start` método se llama en primer lugar, el `ExecuteApplication` se producirá un error en la llamada al método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ActivationContext>  
 <xref:System.AppDomainManager>  
 <xref:System.ApplicationIdentity>  
 [ICLRRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [SetAppDomainManager (método)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)  
 [Tutorial: Descargar ensamblados a petición con la API de implementación ClickOnce mediante el diseñador](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
