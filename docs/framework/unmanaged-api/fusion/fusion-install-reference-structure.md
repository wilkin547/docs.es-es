---
title: FUSION_INSTALL_REFERENCE (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FUSION_INSTALL_REFERENCE
api_location: fusion.dll
api_type: COM
f1_keywords: FUSION_INSTALL_REFERENCE
helpviewer_keywords: FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 36321606fe208233fb6114fe9568b655f0e1b400
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="fusioninstallreference-structure"></a>FUSION_INSTALL_REFERENCE (Estructura)
Representa una referencia que hace que una aplicación a un ensamblado que se ha instalado la aplicación en la caché global de ensamblados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`cbSize`|El tamaño de la estructura, en bytes.|  
|`dwFlags`|Reservado para extensibilidad futura. Este valor debe ser 0 (cero).|  
|`guidScheme`|La entidad que agrega la referencia. Este campo puede tener uno de los siguientes valores:<br /><br /> -FUSION_REFCOUNT_MSI_GUID: Una aplicación que se instala con Microsoft Windows Installer hace referencia al ensamblado. El `szIdentifier` campo está establecido en `MSI`y el `szNonCanonicalData` campo está establecido en `Windows Installer`. Este esquema se utiliza para los ensamblados en paralelo de Windows.<br />-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: El ensamblado hace referencia una aplicación que aparece en el **agregar o quitar programas** interfaz. El `szIdentifier` campo proporciona el símbolo (token) que registra la aplicación con el **agregar o quitar programas** interfaz.<br />-FUSION_REFCOUNT_FILEPATH_GUID: Una aplicación que se representa mediante un archivo en el sistema de archivos hace referencia al ensamblado. El `szIdentifier` campo proporciona la ruta de acceso a este archivo.<br />-FUSION_REFCOUNT_OPAQUE_STRING_GUID: Una aplicación que se representa sólo mediante una cadena opaca hace referencia al ensamblado. El `szIdentifier` campo proporciona esta cadena opaca. La caché global de ensamblados no comprueba la existencia de referencias opacas cuando se quita este valor.<br />-FUSION_REFCOUNT_OSINSTALL_GUID: Este valor está reservado.|  
|`szIdentifier`|Una cadena única que identifica la aplicación que instala al ensamblado en la caché global de ensamblados. Su valor depende del valor de la `guidScheme` campo.|  
|`szNonCanonicalData`|Una cadena que sólo es reconocida por la entidad que agrega la referencia. La caché global de ensamblados almacena esta cadena, pero no la usa.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Fusion.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [Caché global de ensamblados](../../../../docs/framework/app-domains/gac.md)
