---
title: Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea95789ea1623985a6a53fcf923b70d7df2ad460
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170435"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a>Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5
Esta sección describen las interfaces que no administrada de hosts pueden usar para integrar common language runtime (CLR) en el .NET Framework 4, .NET Framework 4.5 y versiones posteriores en sus aplicaciones. Estas interfaces proporcionan métodos para un host configurar y cargar el tiempo de ejecución en un proceso.  
  
 A partir de .NET Framework 4, todas las interfaces de hospedaje tienen las siguientes características:  
  
- Usar administración de la duración (`AddRef` y `Release`), encapsulación (contexto implícito) y `QueryInterface` desde COM.  
  
- No utilice tipos COM como `BSTR`, `SAFEARRAY`, o `VARIANT`.  
  
- Hay no hay modelos de apartamento, agregación o activación del registro que usan el [función CoCreateInstance](https://go.microsoft.com/fwlink/?LinkId=142894).  
  
## <a name="in-this-section"></a>En esta sección  
 [ICLRAppDomainResourceMonitor (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 Proporciona métodos que inspeccionar memoria y uso de CPU de un dominio de aplicación.  
  
 [ICLRDomainManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 Permite que el host especificar el Administrador de dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado y para especificar las propiedades de inicialización.  
  
 [ICLRGCManager2 (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 Proporciona el [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) método, que permite a un host establecer el tamaño del segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados en los valores mayor `DWORD`.  
  
 [ICLRMetaHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 Proporciona métodos que devuelven una versión específica de CLR, enumerar todos los CLR instalados, enumerar todos los tiempos de ejecución en proceso, devuelven la interfaz de activación y detección la versión CLR utilizada para compilar un ensamblado.  
  
 [ICLRMetaHostPolicy (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 Proporciona el [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) método que proporciona una interfaz CLR basándose en criterios de la directiva, ensamblado administrado, versión y archivo de configuración.  
  
 [ICLRRuntimeInfo (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 Proporciona métodos que devuelven información acerca de un tiempo de ejecución específico, incluida la versión, el directorio y el estado de carga.  
  
 [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 Proporciona funciones estáticas globales para básicas para firmar los ensamblados con nombres seguros. Todos los [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) métodos devuelven valores HRESULT de COM estándar.  
  
 [ICLRStrongName2 (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 Proporciona la capacidad para crear nombres seguros mediante el grupo de SHA-2 de algoritmos de Hash seguro (SHA-256, SHA-384 y SHA-512).  
  
 [ICLRTask2 (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 Proporciona toda la funcionalidad de la [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); Además, proporciona métodos que permiten las anulaciones de subprocesos para que se retrasa en el subproceso actual.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Coclases e interfaces de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Describe las interfaces de hospedaje proporcionadas con las versiones 1.0 y 1.1 de .NET Framework.  
  
 [Interfaces de hospedaje de CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 Describe las interfaces de hospedaje proporcionadas con las versiones de .NET Framework 2.0, 3.0 y 3.5.  
  
 [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 Presenta el hospedaje de .NET Framework.
