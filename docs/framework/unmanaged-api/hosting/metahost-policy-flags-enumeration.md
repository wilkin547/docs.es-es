---
title: METAHOST_POLICY_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- METAHOST_POLICY_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_POLICY_FLAGS
helpviewer_keywords:
- METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31ff93b6935c2237a5935c4b40cc30b4129edcd0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230608"
---
# <a name="metahostpolicyflags-enumeration"></a>METAHOST_POLICY_FLAGS (Enumeración)
Proporciona directivas de enlace que son comunes a la mayoría de los hosts en tiempo de ejecución. Esta enumeración se utiliza en el [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) método.  
  
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
|`METAHOST_POLICY_HIGHCOMPAT`|Define la directiva de compatibilidad de alta, que no tiene en cuenta cualquier common language runtime (CLR) que se carga en el proceso actual. En su lugar, considera que sólo el CLR instalados y las preferencias del componente, según se deriva el propio archivo de ensamblado, la versión integrada contra declarada o el archivo de configuración.|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|Aplica la directiva de actualización para el resultado del enlace de versión cuando no se encuentra una coincidencia exacta, según el contenido de HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\Policy\Upgrades. Esto tiene el mismo efecto que [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|Enlace de resultados se devuelven como si la imagen proporcionada a la llamada se lanzaron en un nuevo proceso. Actualmente, `GetRequestedRuntime` omite el conjunto de tiempos de ejecución que se puede cargar y se enlaza con el conjunto de runtimes instalados. Esta marca permite a un host determinar qué tiempo de ejecución de un archivo EXE se enlazará a cuando se inicia.|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|Se muestra un cuadro de diálogo de error si `GetRequestedRuntime` no encuentra un tiempo de ejecución es compatible con los parámetros de entrada. A partir del [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], este cuadro de diálogo de error puede adoptar la forma de un cuadro de diálogo características de Windows que le pregunta si desea que el usuario habilitar la característica correspondiente.|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime` usa la imagen de proceso (y cualquier archivo de configuración correspondiente) como entrada adicional para el proceso de enlace. De forma predeterminada, `GetRequestedRuntime` no recurre a la ruta de acceso de la imagen de proceso (normalmente, el EXE que se usó para iniciar el proceso) al determinar el tiempo de ejecución para enlazar a.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` debe comprobar si la SKU adecuada instalada cuando no hay información disponible en el archivo de configuración. Esto permite que las aplicaciones que no tienen archivos de configuración para generar un error en la SKU más pequeñas que la instalación predeterminada de .NET Framework. De forma predeterminada, `GetRequestedRuntime` no comprueba si está instalada la SKU adecuada a menos que se especifica el atributo SKU en el archivo de configuración `<supportedRuntime />` elemento.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` debe comprobar si la SKU adecuada instalada cuando no hay información disponible en el archivo de configuración. Esto permite que las aplicaciones que no tienen archivos de configuración para generar un error en la SKU más pequeñas que la instalación predeterminada de .NET Framework. De forma predeterminada, `GetRequestedRuntime` no comprueba si está instalada la SKU adecuada a menos que se especifica el atributo SKU en el archivo de configuración `<supportedRuntime />` elemento.|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime` debe ignorar SEM_FAILCRITICALERRORS (que se establece mediante una llamada a la [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) función) y mostrar el cuadro de diálogo de error. De forma predeterminada, SEM_FAILCRITICALERRORS suprime el cuadro de diálogo de error. Puede haber heredado desde otro proceso y el error silencioso puede no ser deseable en su escenario.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Metahost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [Método GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
