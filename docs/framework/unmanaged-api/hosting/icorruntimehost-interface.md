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
ms.openlocfilehash: 420f22a242a20f8bdf5d5b84f47a297a2f503db0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546026"
---
# <a name="icorruntimehost-interface"></a>ICorRuntimeHost (Interfaz)
Proporciona métodos que permiten al host iniciar y detener explícitamente el Common Language Runtime (CLR), para crear y configurar dominios de aplicación, para tener acceso al dominio predeterminado y para enumerar todos los dominios que se ejecutan en el proceso.  
  
 En la versión .NET Framework 2,0, la interfaz es reemplazada por [ICLRRuntimeHost](iclrruntimehost-interface.md).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CloseEnum (Método)](icorruntimehost-closeenum-method.md)|Vuelve a establecer un enumerador de dominio al principio de la lista de dominios.|  
|[Método CreateDomain](icorruntimehost-createdomain-method.md)|Crea un dominio de aplicación. El autor de la llamada recibe un puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de tipo <xref:System.AppDomain?displayProperty=nameWithType> .|  
|[Método CreateDomainEx](icorruntimehost-createdomainex-method.md)|Crea un dominio de aplicación. Este método permite al llamador pasar una instancia de IAppDomainSetup para configurar características adicionales de la instancia de devuelta <xref:System._AppDomain> .|  
|[Método CreateDomainSetup](icorruntimehost-createdomainsetup-method.md)|Obtiene un puntero de interfaz de tipo `IAppDomainSetup` a una <xref:System.AppDomainSetup> instancia de. `IAppDomainSetup` proporciona métodos para configurar aspectos de un dominio de aplicación antes de que se cree.|  
|[Método CreateEvidence](icorruntimehost-createevidence-method.md)|Obtiene un puntero de interfaz de tipo <xref:System.Security.Principal.IIdentity> , que permite al host crear evidencia de seguridad para pasar a [CreateDomain](icorruntimehost-createdomain-method.md) o [createdomainex (](icorruntimehost-createdomainex-method.md).|  
|[Método CreateLogicalThreadState](icorruntimehost-createlogicalthreadstate-method.md)|No utilizar.|  
|[Método CurrentDomain](icorruntimehost-currentdomain-method.md)|Obtiene un puntero de interfaz de tipo <xref:System._AppDomain> que representa el dominio cargado en el subproceso actual.|  
|[Método DeleteLogicalThreadState](icorruntimehost-deletelogicalthreadstate-method.md)|No utilizar.|  
|[Método EnumDomains](icorruntimehost-enumdomains-method.md)|Obtiene un enumerador para los dominios en el proceso actual.|  
|[GetConfiguration (método)](icorruntimehost-getconfiguration-method.md)|Obtiene un objeto que permite al host especificar la configuración de devolución de llamada de CLR.|  
|[Método GetDefaultDomain](icorruntimehost-getdefaultdomain-method.md)|Obtiene un puntero de interfaz de tipo <xref:System._AppDomain> que representa el dominio predeterminado para el proceso actual.|  
|[Método LocksHeldByLogicalThread](icorruntimehost-locksheldbylogicalthread-method.md)|No utilizar.|  
|[Método MapFile](icorruntimehost-mapfile-method.md)|Asigna el archivo especificado a la memoria. Este método está obsoleto.|  
|[Método NextDomain](icorruntimehost-nextdomain-method.md)|Obtiene un puntero de interfaz al siguiente dominio en la enumeración.|  
|[Start (método)](icorruntimehost-start-method.md)|Inicia el CLR.|  
|[STOP (método)](icorruntimehost-stop-method.md)|Detiene la ejecución de código en tiempo de ejecución para el proceso actual.|  
|[Método SwitchInLogicalThreadState](icorruntimehost-switchinlogicalthreadstate-method.md)|No utilizar.|  
|[Método SwitchOutLogicalThreadState](icorruntimehost-switchoutlogicalthreadstate-method.md)|No utilizar.|  
|[Método UnloadDomain](icorruntimehost-unloaddomain-method.md)|Descarga el dominio de aplicación especificado del proceso actual.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:** 1,0, 1,1  
  
## <a name="see-also"></a>Vea también

- <xref:System.AppDomain>
- [Hospedar aplicaciones de WPF](index.md)
- [ICLRRuntimeHost (Interfaz)](iclrruntimehost-interface.md)
- [Hosts de runtime](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))
- [Interfaces de hospedaje](hosting-interfaces.md)
- [CorRuntimeHost (Coclase)](corruntimehost-coclass.md)
