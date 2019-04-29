---
title: CorBindToRuntime (Función)
ms.date: 03/30/2017
api_name:
- CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntime
helpviewer_keywords:
- CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb5c05a88c12b5124c77b0d0a7f834b405dd289f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697425"
---
# <a name="corbindtoruntime-function"></a>CorBindToRuntime (Función)
Permite a los hosts no administrados cargar Common Language Runtime (CLR) en un proceso.  
  
 Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,   
    [in]  LPCWSTR     pwszBuildFlavor,   
    [in]  REFCLSID    rclsid,   
    [in]  REFIID      riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwszVersion`  
 [in] Cadena que describe la versión de CLR que se desea cargar.  
  
 Un número de versión de .NET Framework consta de cuatro partes separadas por puntos: *principal.secundaria.compilación.revisión*. La cadena que se pasó como `pwszVersion` debe comenzar con el carácter "v" seguido de las primeras tres partes del número de versión (por ejemplo, "v1.0.1529").  
  
 Algunas versiones de CLR se instalan con una instrucción de directiva que especifica la compatibilidad con versiones anteriores de CLR. De forma predeterminada, el proceso intermedio ("shim") de inicio evalúa `pwszVersion` con las instrucciones de directiva y carga la versión más reciente del runtime compatible con la versión solicitada. Un host puede hacer que el proceso intermedio ("shim") omita la evaluación de directivas y cargue exactamente la versión especificada en `pwszVersion`, pasando el valor `STARTUP_LOADER_SAFEMODE` para el parámetro `flags`, como se describe a continuación.  
  
 Si el llamador especifica null para `pwszVersion`, se carga la versión más reciente del tiempo de ejecución. Pasar null no impide al host ningún control sobre el que se carga la versión del tiempo de ejecución. Aunque este planteamiento puede ser apropiado en algunos escenarios, se recomienda encarecidamente que el host proponga cargar una versión específica.  
  
 `pwszBuildFlavor`  
 [in] Cadena que especifica si se debe cargar la compilación de CLR para servidor o para estación de trabajo. Los valores válidos son `svr` y `wks`. La compilación para servidor está optimizada para aprovechar las ventajas que aportan varios procesadores al realizar recolecciones de elementos no utilizados, mientras que la compilación para estación de trabajo está optimizada para aplicaciones cliente que se ejecutan en equipos con un solo procesador.  
  
 Si `pwszBuildFlavor` está establecido en null, se cargará la compilación para estación de trabajo. Cuando se ejecuta en un equipo con un solo procesador, siempre se cargará la compilación de la estación de trabajo, incluso si `pwszBuildFlavor` está establecido en `svr`. Sin embargo, si `pwszBuildFlavor` está establecido en `svr` y se especifica una colección de elementos no utilizados simultánea (vea la descripción de la `flags` parámetro), se cargará la compilación de servidor.  
  
 `rclsid`  
 [in] El `CLSID` de la coclase que implementa el [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaz. Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 [in] `IID` de la interfaz solicitada de `rclsid`. Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 [out] Puntero de interfaz devuelto a `riid`.  
  
## <a name="remarks"></a>Comentarios  
 Si `pwszVersion` especifica una versión del runtime que no existe, `CorBindToRuntimeEx` devuelve un valor HRESULT de CLR_E_SHIM_RUNTIMELOAD.  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>Flujo y contexto de ejecución de la identidad de Windows  
 En la versión 1 de CLR, el objeto <xref:System.Security.Principal.WindowsIdentity> no fluye por puntos asincrónicos, como nuevos subprocesos, grupos de subprocesos o devoluciones de llamada de temporizador. En la versión 2.0 de CLR, el objeto <xref:System.Threading.ExecutionContext> ajusta cierta información sobre el subproceso en ejecución y hace que fluya por cualquier punto asincrónico, pero no por los límites del dominio de aplicación. De igual forma, el objeto <xref:System.Security.Principal.WindowsIdentity> también fluye por cualquier punto asincrónico. Por consiguiente, también fluye la suplantación actual en el subproceso, si la hubiera.  
  
 El flujo puede modificarse de dos maneras:  
  
1. Si se modifica la configuración de <xref:System.Threading.ExecutionContext> para suprimir el flujo por subproceso (vea los métodos <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A> y <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A>).  
  
2. Si se cambia el modo predeterminado del proceso al modo de compatibilidad de la versión 1, donde el objeto <xref:System.Security.Principal.WindowsIdentity> no fluye por ningún punto asincrónico, independientemente de los valores de <xref:System.Threading.ExecutionContext> en el subproceso actual. La manera de cambiar el modo predeterminado depende de si se usa un archivo ejecutable administrado o una interfaz de hospedaje no administrada para cargar CLR:  
  
    1. Para los archivos ejecutables administrados, se debe establecer el `enabled` atributo de la [ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) elemento `true`.  
  
    2. Para las interfaces de hospedaje no administradas, se establece la marca `STARTUP_LEGACY_IMPERSONATION` en el parámetro `flags` al llamar a la función `CorBindToRuntimeEx`.  
  
     El modo de compatibilidad de la versión 1 se aplica a todo el proceso y a todos los dominios de aplicación del proceso.  
  
## <a name="remarks"></a>Comentarios  
 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) y `CorBindToRuntime` realizar la misma operación, pero la `CorBindToRuntimeEx` función le permite establecer marcas para especificar el comportamiento de CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CorBindToCurrentRuntime (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntimeByCfg (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [ICorRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
