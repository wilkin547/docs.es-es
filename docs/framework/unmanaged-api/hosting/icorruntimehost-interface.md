---
title: ICorRuntimeHost (Interfaz)
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
- ICorRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost
helpviewer_keywords:
- ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1280c49c2eea6a06eca10ebd8896b0722e321547
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="icorruntimehost-interface"></a>ICorRuntimeHost (Interfaz)
Proporciona métodos que permiten al host iniciar y detener de forma explícita, common language runtime (CLR) para crear y configurar dominios de aplicación, tener acceso al dominio predeterminado y enumerar todos los dominios que se ejecuta en el proceso.  
  
 En la versión 2.0 de .NET Framework, esta interfaz ha sido reemplazada por [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CloseEnum (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|Restablece un enumerador de dominio al principio de la lista de dominios.|  
|[CreateDomain (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|Crea un dominio de aplicación. El llamador recibe un puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de tipo <xref:System.AppDomain?displayProperty=nameWithType>.|  
|[CreateDomainEx (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|Crea un dominio de aplicación. Este método permite al llamador pasar una instancia de IAppDomainSetup para configurar características adicionales de devuelto <xref:System._AppDomain> instancia.|  
|[CreateDomainSetup (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|Obtiene un puntero de interfaz de tipo `IAppDomainSetup` a una <xref:System.AppDomainSetup> instancia. `IAppDomainSetup`Proporciona métodos para configurar aspectos de un dominio de aplicación antes de que se crea.|  
|[CreateEvidence (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|Obtiene un puntero de interfaz de tipo <xref:System.Security.Principal.IIdentity>, que permite al host crear la evidencia de seguridad que se pasarán a [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) o [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).|  
|[CreateLogicalThreadState (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|No utilizar.|  
|[CurrentDomain (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|Obtiene un puntero de interfaz de tipo <xref:System._AppDomain> que representa el dominio cargado en el subproceso actual.|  
|[DeleteLogicalThreadState (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|No utilizar.|  
|[EnumDomains (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|Obtiene un enumerador para los dominios en el proceso actual.|  
|[GetConfiguration (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|Obtiene un objeto que permite al host especificar la configuración de devolución de llamada de CLR.|  
|[GetDefaultDomain (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|Obtiene un puntero de interfaz de tipo <xref:System._AppDomain> que representa el dominio predeterminado para el proceso actual.|  
|[LocksHeldByLogicalThread (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|No utilizar.|  
|[MapFile (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|Asigna el archivo especificado en la memoria. Este método está obsoleto.|  
|[NextDomain (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|Obtiene un puntero de interfaz al dominio siguiente de la enumeración.|  
|[Start (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|Inicia el CLR.|  
|[Stop (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|Detiene la ejecución de código en tiempo de ejecución para el proceso actual.|  
|[SwitchInLogicalThreadState (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|No utilizar.|  
|[SwitchOutLogicalThreadState (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|No utilizar.|  
|[UnloadDomain (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|Descarga el dominio de aplicación especificado del proceso actual.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>Vea también  
 <xref:System.AppDomain>  
 [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [ICLRRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [Hosts en tiempo de ejecución](http://msdn.microsoft.com/library/99d9246a-b994-4fe5-985c-8588d1d59998)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CorRuntimeHost (coclase)](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
