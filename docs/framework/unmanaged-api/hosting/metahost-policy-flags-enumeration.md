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
ms.openlocfilehash: 048286fb9e1af34cd964fb5b21892778f9575d2c
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938201"
---
# <a name="metahost_policy_flags-enumeration"></a>METAHOST_POLICY_FLAGS (Enumeración)
Proporciona directivas de enlace que son comunes a la mayoría de los hosts en tiempo de ejecución. Esta enumeración la usa el método [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`METAHOST_POLICY_HIGHCOMPAT`|Define la Directiva de alta compatibilidad, que no tiene en cuenta ningún Common Language Runtime (CLR) que se cargue en el proceso actual. En su lugar, solo tiene en cuenta el CLR instalado y las preferencias del componente, como se derivan del propio archivo de ensamblado, la versión de compilación compilada declarada o el archivo de configuración.|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|Aplica la Directiva de actualización al resultado del enlace de la versión cuando no se encuentra una coincidencia exacta, en función del contenido de HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\\. NETFramework\Policy\Upgrades. Esto tiene el mismo efecto que [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|Se devuelven los resultados de enlace como si la imagen proporcionada a la llamada se iniciara en un nuevo proceso. Actualmente, `GetRequestedRuntime` omite el conjunto de tiempos de ejecución cargables y enlaces con el conjunto de tiempos de ejecución instalados. Esta marca permite a un host determinar en qué tiempo de ejecución se enlazará un archivo EXE cuando se inicie.|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|Se muestra un cuadro de diálogo de error si `GetRequestedRuntime` no puede encontrar un tiempo de ejecución que sea compatible con los parámetros de entrada. A partir de la .NET Framework 4,5, este cuadro de diálogo de error puede adoptar la forma de un cuadro de diálogo de característica de Windows que pregunta si el usuario desea habilitar la característica adecuada.|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime` usa la imagen de proceso (y cualquier archivo de configuración correspondiente) como entrada adicional para el proceso de enlace. De forma predeterminada, `GetRequestedRuntime` no revierte a la ruta de acceso de la imagen de proceso (normalmente, el archivo EXE que se usó para iniciar el proceso) al determinar el Runtime con el que se va a enlazar.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` debe comprobar si la SKU adecuada está instalada cuando no hay información disponible en el archivo de configuración. Esto permite que las aplicaciones que no tienen archivos de configuración no funcionen correctamente en SKU más pequeñas que la instalación predeterminada del .NET Framework. De forma predeterminada, `GetRequestedRuntime` no comprueba si se instala la SKU adecuada a menos que el atributo SKU se especifique en el archivo de configuración `<supportedRuntime />` elemento.|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime` debe omitir SEM_FAILCRITICALERRORS (que se establece mediante una llamada a la función [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) ) y mostrar el cuadro de diálogo de error. De forma predeterminada, SEM_FAILCRITICALERRORS suprime el cuadro de diálogo de error. Es posible que se haya heredado de otro proceso y que el error silencioso no sea deseable en el escenario.|  
  
## <a name="remarks"></a>Notas  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [GetRequestedRuntime (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
