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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed32fe643a7722eaf1af38e6079096194690e950
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211403"
---
# <a name="iclrruntimehost-interface"></a>ICLRRuntimeHost (Interfaz)
Proporciona una funcionalidad similar a la de la [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interfaz proporcionada en .NET Framework versión 1, con los cambios siguientes:  
  
-   La adición de la [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) método para establecer la interfaz de control host.  
  
-   La omisión de algunos métodos proporcionados por `ICorRuntimeHost`.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|Se utiliza en escenarios de implementación de ClickOnce basada en manifiestos para especificar la aplicación que debe activarse en un nuevo dominio.|  
|[Método ExecuteInAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|Especifica el <xref:System.AppDomain> en el que se va a ejecutar el código administrado especificado.|  
|[Método ExecuteInDefaultAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|Invoca el método especificado del tipo especificado en el ensamblado especificado.|  
|[Método GetCLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|Obtiene un puntero de interfaz de tipo [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) que los hosts pueden usar para personalizar algunos aspectos de common language runtime (CLR).|  
|[Método GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|Obtiene el identificador numérico de la <xref:System.AppDomain> que se está ejecutando actualmente.|  
|[Método SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|Establece la interfaz de control host. Debe llamar a `SetHostControl` antes de llamar a `Start`.|  
|[Método Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|Inicializa CLR en un proceso.|  
|[Método Stop](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|Detiene la ejecución de código por el tiempo de ejecución.|  
|[Método UnloadAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|Descarga el <xref:System.AppDomain> que se corresponde con el identificador numérico especificado.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], utilice el [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interfaz para obtener un puntero a la [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz y, a continuación, llame a la [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) método para obtener un puntero a `ICLRRuntimeHost`. En versiones anteriores de .NET Framework, el host obtiene un puntero a un `ICLRRuntimeHost` instancia mediante una llamada a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md). Para proporcionar implementaciones de cualquiera de las tecnologías proporcionadas en la versión 2.0 de .NET Framework, debe usar `ICLRRuntimeHost` en lugar de `ICorRuntimeHost`.  
  
> [!IMPORTANT]
>  No llame a la [iniciar](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) método antes de llamar a la [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) método para activar una aplicación basada en manifiesto. Si el `Start` se llama al método en primer lugar, el `ExecuteApplication` se producirá un error en la llamada al método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CorBindToCurrentRuntime (Función)](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntimeEx (Función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [ICLRControl (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICorRuntimeHost (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CLRRuntimeHost (Coclase)](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
