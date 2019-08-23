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
ms.openlocfilehash: 38938de335e5f0d7cb8051554c400f16df012362
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965354"
---
# <a name="iclrruntimehostexecuteapplication-method"></a>ICLRRuntimeHost::ExecuteApplication (Método)
Se usa en escenarios de implementación ClickOnce basados en manifiesto para especificar la aplicación que se va a activar en un dominio nuevo. Para obtener más información acerca de estos escenarios, consulte [seguridad e implementación de ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzAppFullName`  
 de Nombre completo de la aplicación, tal y como se <xref:System.ApplicationIdentity>define para.  
  
 `dwManifestPaths`  
 de Número de cadenas contenidas en `ppwzManifestPaths` la matriz.  
  
 `ppwzManifestPaths`  
 [in] Opcional. Matriz de cadenas que contiene las rutas de acceso de manifiesto para la aplicación.  
  
 `dwActivationData`  
 de Número de cadenas contenidas en `ppwzActivationData` la matriz.  
  
 `ppwzActivationData`  
 [in] Opcional. Una matriz de cadenas que contiene los datos de activación de la aplicación, como la parte de la cadena de consulta de la dirección URL de las aplicaciones implementadas a través de la Web.  
  
 `pReturnValue`  
 enuncia El valor devuelto desde el punto de entrada de la aplicación.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|DESCRIPCIÓN|  
|-------------|-----------------|  
|S_OK|`ExecuteApplication`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 `ExecuteApplication`se utiliza para activar las aplicaciones ClickOnce en un dominio de aplicación recién creado.  
  
 El `pReturnValue` parámetro de salida se establece en el valor devuelto por la aplicación. Si proporciona un valor null para `pReturnValue`, `ExecuteApplication` no producirá un error, pero no devolverá ningún valor.  
  
> [!IMPORTANT]
> No llame al método [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) antes de llamar `ExecuteApplication` al método para activar una aplicación basada en manifiesto. Si se `Start` llama primero al método, se `ExecuteApplication` producirá un error en la llamada al método.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [ICLRRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [SetAppDomainManager (método)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [Tutorial: Descarga de ensamblados a petición con la API de implementación ClickOnce mediante el diseñador](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
