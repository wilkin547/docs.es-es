---
title: ICorRuntimeHost (Interfaz)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41dc37751e2dcf26eea887e84423179512c53614
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653520"
---
# <a name="icorruntimehost-interface"></a>ICorRuntimeHost (Interfaz)
Proporciona métodos que permiten al host iniciar y detener de forma explícita, common language runtime (CLR) para crear y configurar dominios de aplicación, tener acceso al dominio de forma predeterminada y para enumerar todos los dominios que se ejecutan en el proceso.  
  
 En la versión 2.0 de .NET Framework, esta interfaz ha sido reemplazada por [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CloseEnum (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|Restablece un enumerador de dominio al principio de la lista de dominios.|  
|[CreateDomain (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|Crea un dominio de aplicación. El llamador recibe un puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de tipo <xref:System.AppDomain?displayProperty=nameWithType>.|  
|[CreateDomainEx (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|Crea un dominio de aplicación. Este método permite al llamador pasar una instancia de IAppDomainSetup para configurar características adicionales de devuelto <xref:System._AppDomain> instancia.|  
|[CreateDomainSetup (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|Obtiene un puntero de interfaz de tipo `IAppDomainSetup` a un <xref:System.AppDomainSetup> instancia. `IAppDomainSetup` Proporciona métodos para configurar aspectos de un dominio de aplicación antes de crearlo.|  
|[CreateEvidence (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|Obtiene un puntero de interfaz de tipo <xref:System.Security.Principal.IIdentity>, que permite al host crear la evidencia de seguridad para pasar a [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) o [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).|  
|[CreateLogicalThreadState (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|No utilizar.|  
|[CurrentDomain (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|Obtiene un puntero de interfaz de tipo <xref:System._AppDomain> que representa el dominio cargado en el subproceso actual.|  
|[DeleteLogicalThreadState (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|No utilizar.|  
|[EnumDomains (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|Obtiene un enumerador para los dominios en el proceso actual.|  
|[GetConfiguration (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|Obtiene un objeto que permite al host especificar la configuración de devolución de llamada de CLR.|  
|[GetDefaultDomain (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|Obtiene un puntero de interfaz de tipo <xref:System._AppDomain> que representa el dominio predeterminado para el proceso actual.|  
|[LocksHeldByLogicalThread (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|No utilizar.|  
|[MapFile (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|Asigna el archivo especificado en la memoria. Este método está obsoleto.|  
|[NextDomain (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|Obtiene un puntero de interfaz al siguiente dominio de la enumeración.|  
|[Start (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|Inicia el CLR.|  
|[Stop (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|Detiene la ejecución de código en tiempo de ejecución para el proceso actual.|  
|[SwitchInLogicalThreadState (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|No utilizar.|  
|[SwitchOutLogicalThreadState (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|No utilizar.|  
|[UnloadDomain (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|Descarga el dominio de aplicación especificado del proceso actual.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>Vea también
- <xref:System.AppDomain>
- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [ICLRRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [Hosts de runtime](https://msdn.microsoft.com/library/99d9246a-b994-4fe5-985c-8588d1d59998)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CorRuntimeHost (coclase)](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
