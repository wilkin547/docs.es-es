---
title: Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
ms.openlocfilehash: a524c0b0e01fbde95ce2341874511960b3e5738e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616858"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a>Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5
En esta sección se describen las interfaces que los hosts no administrados pueden utilizar para integrar el Common Language Runtime (CLR) en el .NET Framework 4, .NET Framework 4,5 y versiones posteriores en sus aplicaciones. Estas interfaces proporcionan métodos para que un host configure y cargue el tiempo de ejecución en un proceso.  
  
 A partir de la .NET Framework 4, todas las interfaces de hospedaje tienen las siguientes características:  
  
- Usan la administración de la duración ( `AddRef` y `Release` ), la encapsulación (contexto implícito) y `QueryInterface` desde com.  
  
- No utilizan tipos COM como `BSTR` , `SAFEARRAY` o `VARIANT` .  
  
- No hay ningún modelo de apartamento, agregación o activación del registro que use la [función CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).  
  
## <a name="in-this-section"></a>En esta sección  
 [ICLRAppDomainResourceMonitor (Interfaz)](iclrappdomainresourcemonitor-interface.md)  
 Proporciona métodos que inspeccionan el uso de la CPU y la memoria de un dominio de aplicación.  
  
 [ICLRDomainManager (Interfaz)](iclrdomainmanager-interface.md)  
 Permite al host especificar el administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado y para especificar las propiedades de inicialización.  
  
 [ICLRGCManager2 (Interfaz)](iclrgcmanager2-interface.md)  
 Proporciona el método [setgcstartuplimitsex (](iclrgcmanager2-setgcstartuplimitsex-method.md) , que permite a un host establecer el tamaño del segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados en valores mayores que `DWORD` .  
  
 [ICLRMetaHost (Interfaz)](iclrmetahost-interface.md)  
 Proporciona métodos que devuelven una versión específica de CLR, enumeran todos los CLR instalados, enumeran todos los tiempos de ejecución en proceso, devuelven la interfaz de activación y detectan la versión de CLR utilizada para compilar un ensamblado.  
  
 [ICLRMetaHostPolicy (Interfaz)](iclrmetahostpolicy-interface.md)  
 Proporciona el método [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) que proporciona una interfaz CLR basada en los criterios de la Directiva, el ensamblado administrado, la versión y el archivo de configuración.  
  
 [ICLRRuntimeInfo (Interfaz)](iclrruntimeinfo-interface.md)  
 Proporciona métodos que devuelven información acerca de un Runtime específico, incluidos el estado de la versión, el directorio y la carga.  
  
 [ICLRStrongName (Interfaz)](iclrstrongname-interface.md)  
 Proporciona funciones estáticas globales básicas para firmar ensamblados con nombres seguros. Todos los métodos [ICLRStrongName](iclrstrongname-interface.md) devuelven valores HRESULT de com estándar.  
  
 [ICLRStrongName2 (Interfaz)](iclrstrongname2-interface.md)  
 Proporciona la capacidad de crear nombres seguros mediante el grupo SHA-2 de algoritmos de hash seguro (SHA-256, SHA-384 y SHA-512).  
  
 [ICLRTask2 (Interfaz)](iclrtask2-interface.md)  
 Proporciona toda la funcionalidad de la [interfaz ICLRTask](iclrtask-interface.md); Además, proporciona métodos que permiten que las anulaciones de subprocesos se retrasen en el subproceso actual.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Coclases e interfaces de hospedaje de CLR en desuso](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Describe las interfaces de hospedaje proporcionadas con las versiones .NET Framework 1,0 y 1,1.  
  
 [Interfaces de hospedaje de CLR](clr-hosting-interfaces.md)  
 Describe las interfaces de hospedaje proporcionadas con las .NET Framework versiones 2,0, 3,0 y 3,5.  
  
 [Hospedar aplicaciones de WPF](index.md)  
 Introduce el hospedaje en el .NET Framework.
