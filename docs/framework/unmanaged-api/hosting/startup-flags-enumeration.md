---
title: "STARTUP_FLAGS (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: STARTUP_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: STARTUP_FLAGS
helpviewer_keywords: STARTUP_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 4f043594-0c45-4bc6-988e-a6793f0d8d06
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca2db0cd7082a596999f1d74c9092264a65692ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="startupflags-enumeration"></a>STARTUP_FLAGS (Enumeración)
Contiene valores que indican el comportamiento de inicio de Common Language Runtime (CLR). De manera predeterminada, la recolección de elementos no utilizados es no simultánea y solo se carga la biblioteca de clases base en el área neutral con respecto al dominio.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    STARTUP_CONCURRENT_GC                         = 0x1,  
    STARTUP_LOADER_OPTIMIZATION_MASK              = 0x3<<1,  
    STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN     = 0x1<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN      = 0x2<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST = 0x3<<1,  
  
    STARTUP_LOADER_SAFEMODE                       = 0x10,  
    STARTUP_LOADER_SETPREFERENCE                  = 0x100,  
  
    STARTUP_SERVER_GC                             = 0x1000,  
    STARTUP_HOARD_GC_VM                           = 0x2000,  
  
    STARTUP_SINGLE_VERSION_HOSTING_INTERFACE      = 0x4000,  
    STARTUP_LEGACY_IMPERSONATION                  = 0x10000,  
    STARTUP_DISABLE_COMMITTHREADSTACK             = 0x20000,  
    STARTUP_ALWAYSFLOW_IMPERSONATION              = 0x40000,  
    STARTUP_TRIM_GC_COMMIT                        = 0x80000,  
  
    STARTUP_ETW                                   = 0x100000,  
    STARTUP_ARM                                   = 0x400000  
} STARTUP_FLAGS;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|Especifica que se debería utilizar la recolección de elementos no utilizados simultánea. Si el llamador solicita la compilación para servidor y la recolección de elementos no utilizados simultánea en un equipo con un solo procesador, se ejecuta, en su lugar, la versión para estación de trabajo y la recolección no simultánea de elementos no utilizados. **Nota:** no se admite la recolección simultánea en aplicaciones que se ejecutan WOW64 x86 emulador en sistemas de 64 bits que implementan la arquitectura Intel Itanium (denominada anteriormente IA-64). Para obtener más información sobre el uso de WOW64 en sistemas de Windows de 64 bits, consulte [aplicaciones Running 32 bits](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|Especifica que se producirá la optimización del cargador.|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|Especifica que ningún ensamblado se carga como neutral con respecto al dominio.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|Especifica que todos los ensamblados se cargan como neutrales con respecto al dominio.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|Especifica que todos los ensamblados de nombre seguro se cargan como neutrales con respecto al dominio.|  
|`STARTUP_LOADER_SAFEMODE`|Especifica que la directiva de versión de CLR no se aplicará a la versión pasada. Se cargará la versión exacta especificada de CLR. El proceso intermedio ("shim") no evalúa directivas para determinar la última versión compatible.|  
|`STARTUP_LOADER_SETPREFERENCE`|Especifica que se establecerá el motor en tiempo de ejecución preferido, pero en realidad no se iniciará.|  
|`STARTUP_SERVER_GC`|Especifica que se usará la recolección de elementos no utilizados del servidor.|  
|`STARTUP_HOARD_GC_VM`|Especifica que la recolección de elementos no utilizados mantendrá la dirección virtual usada.|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|Especifica que no se permitirá combinar una interfaz de hospedaje.|  
|`STARTUP_LEGACY_IMPERSONATION`|Especifica que la suplantación no debería fluir de forma predeterminada por puntos asincrónicos.|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|Especifica que no se debería confirmar la pila de subprocesos completa cuando el subproceso inicia el funcionamiento.|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|Especifica que las suplantaciones administradas y las suplantaciones logradas a través de la invocación de plataforma fluirán por puntos asincrónicos. De forma predeterminada, solo las suplantaciones administradas fluirán por puntos asincrónicos.|  
|`STARTUP_TRIM_GC_COMMIT`|Especifica que la recolección de elementos no utilizados usará el espacio menos confirmado cuando quede poca memoria del sistema. Vea `gcTrimCommitOnLowMemory` en [la optimización de hospedaje Web compartido](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md).|  
|`STARTUP_ETW`|Especifica que el seguimiento de eventos para Windows (ETW) está habilitado para los eventos de Common Language Runtime. A partir de Windows Vista, el seguimiento de eventos siempre está habilitado, por lo que esta marca no tiene ningún efecto. Vea [controlar el registro de .NET Framework](../../../../docs/framework/performance/controlling-logging.md).|  
|`STARTUP_ARM`|Especifica que la supervisión de recursos de dominio de aplicación está habilitada. Consulte la <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> propiedad y [ \<appDomainResourceMonitoring > elemento](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
