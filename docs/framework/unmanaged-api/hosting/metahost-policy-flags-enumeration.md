---
title: "METAHOST_POLICY_FLAGS (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: METAHOST_POLICY_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: METAHOST_POLICY_FLAGS
helpviewer_keywords: METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8946fdcc7c23e11a3f3d78070532ac0bf72b33b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="metahostpolicyflags-enumeration"></a>METAHOST_POLICY_FLAGS (Enumeración)
Proporciona directivas de enlace que son comunes a la mayoría de los hosts en tiempo de ejecución. Esta enumeración se usa en la [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    METAHOST_POLICY_HIGHCOMPAT              = 0x00,  
    METAHOST_POLICY_APPLY_UPGRADE_POLICY    = 0x08,  
    METAHOST_POLICY_EMULATE_EXE_LAUNCH      = 0x10,  
    METAHOST_POLICY_SHOW_ERROR_DIALOG       = 0x20,  
    METAHOST_POLICY_USE_PROCESS_IMAGE_PATH  = 0x40,  
    METAHOST_POLICY_ENSURE_SKU_SUPPORTED    = 0x80,  
    METAHOST_POLICY_IGNORE_ERROR_MODE       = 0x1000  
  
} METAHOST_POLICY_FLAGS;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|Define la directiva de compatibilidad de alta, que no tiene en cuenta cualquier common language runtime (CLR) que se carga en el proceso actual. En su lugar, considera que solo los CLR instalados y las preferencias del componente, que se deriva el propio archivo de ensamblado, la versión compilada con declarado o el archivo de configuración.|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|Aplica la directiva de actualización en el resultado de enlace de versión cuando no se encuentra una coincidencia exacta, en función del contenido de HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\Policy\Upgrades. Esto tiene el mismo efecto que [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|Enlace de resultados se devuelve como si la imagen proporcionada a la llamada se iniciara en un nuevo proceso. Actualmente, `GetRequestedRuntime` pasa por alto el conjunto de versiones cargables de Runtime y la enlaza con el conjunto de Runtime instalados. Esta marca permite a un host determinar qué en tiempo de ejecución un archivo EXE se enlazará a cuando se inicia.|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|Se muestra un cuadro de diálogo de error si `GetRequestedRuntime` no puede encontrar un tiempo de ejecución que sea compatible con los parámetros de entrada. A partir del [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], este cuadro de diálogo de error puede adoptar la forma de un cuadro de diálogo de característica de Windows que le pregunta si desea que el usuario habilitar la característica adecuada.|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime`utiliza la imagen de proceso (y cualquier archivo de configuración correspondiente) como entrada adicional para el proceso de enlace. De forma predeterminada, `GetRequestedRuntime` no regresa a la ruta de acceso de imagen de proceso (normalmente, el EXE que se usó para iniciar el proceso) al determinar el tiempo de ejecución para enlazar a.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime`debe comprobar si se instala el SKU adecuado cuando no hay información disponible en el archivo de configuración. Esto permite a las aplicaciones que no tienen archivos de configuración que producen errores leves en SKU más pequeñas que la instalación predeterminada de .NET Framework. De forma predeterminada, `GetRequestedRuntime` no comprueba si se instala el SKU adecuado a menos que se especifica el atributo SKU en el archivo de configuración `<supportedRuntime />` elemento.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime`debe comprobar si se instala el SKU adecuado cuando no hay información disponible en el archivo de configuración. Esto permite a las aplicaciones que no tienen archivos de configuración que producen errores leves en SKU más pequeñas que la instalación predeterminada de .NET Framework. De forma predeterminada, `GetRequestedRuntime` no comprueba si se instala el SKU adecuado a menos que se especifica el atributo SKU en el archivo de configuración `<supportedRuntime />` elemento.|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime`debe ignorar SEM_FAILCRITICALERRORS (que se establece mediante una llamada a la [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) función) y mostrar el cuadro de diálogo de error. De forma predeterminada, SEM_FAILCRITICALERRORS suprime el cuadro de diálogo de error. Puede haber heredado desde otro proceso y el error silencioso puede no ser deseable en el escenario.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Metahost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [GetRequestedRuntime (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
