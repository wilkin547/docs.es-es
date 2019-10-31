---
title: ICLRRuntimeHost (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
ms.openlocfilehash: 568c63681b84d0ab3642d84e4a6715ad230582db
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120387"
---
# <a name="iclrruntimehost-interface"></a>ICLRRuntimeHost (Interfaz)
Proporciona una funcionalidad similar a la de la interfaz [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) proporcionada en el .NET Framework versión 1, con los siguientes cambios:  
  
- La adición del método [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) para establecer la interfaz de control host.  
  
- La omisión de algunos métodos proporcionados por `ICorRuntimeHost`.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ExecuteApplication (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|Se usa en escenarios de implementación ClickOnce basados en manifiesto para especificar la aplicación que se va a activar en un dominio nuevo.|  
|[ExecuteInAppDomain (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|Especifica el <xref:System.AppDomain> en el que se va a ejecutar el código administrado especificado.|  
|[ExecuteInDefaultAppDomain (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|Invoca el método especificado del tipo especificado en el ensamblado especificado.|  
|[GetCLRControl (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|Obtiene un puntero de interfaz de tipo [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) que los hosts pueden utilizar para personalizar los aspectos del Common Language Runtime (CLR).|  
|[GetCurrentAppDomainId (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|Obtiene el identificador numérico de la <xref:System.AppDomain> que se está ejecutando actualmente.|  
|[SetHostControl (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|Establece la interfaz de control host. Debe llamar a `SetHostControl` antes de llamar a `Start`.|  
|[Start (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|Inicializa CLR en un proceso.|  
|[Stop (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|Detiene la ejecución del código en tiempo de ejecución.|  
|[UnloadAppDomain (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|Descarga el <xref:System.AppDomain> que corresponde al identificador numérico especificado.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de la .NET Framework 4, use la interfaz [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) para obtener un puntero a la interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) y, a continuación, llame al método [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) para obtener un puntero a `ICLRRuntimeHost`. En versiones anteriores del .NET Framework, el host obtiene un puntero a una instancia de `ICLRRuntimeHost` llamando a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime (](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md). Para proporcionar implementaciones de cualquiera de las tecnologías que se proporcionan en la .NET Framework versión 2,0, debe utilizar `ICLRRuntimeHost` en lugar de `ICorRuntimeHost`.  
  
> [!IMPORTANT]
> No llame al método [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) antes de llamar al método [ExecuteApplication (](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) para activar una aplicación basada en manifiesto. Si se llama primero al método `Start`, se producirá un error en la llamada al método `ExecuteApplication`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CorBindToCurrentRuntime (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntimeEx (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICorRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CLRRuntimeHost (coclase)](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
