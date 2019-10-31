---
title: FUSION_INSTALL_REFERENCE (Estructura)
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
ms.openlocfilehash: 3859752fd92a76f3fef1ceced0e792109b65106a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108277"
---
# <a name="fusion_install_reference-structure"></a>FUSION_INSTALL_REFERENCE (Estructura)
Representa una referencia que una aplicación realiza a un ensamblado que la aplicación ha instalado en la caché global de ensamblados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`cbSize`|Tamaño de la estructura en bytes.|  
|`dwFlags`|Reservado para extensibilidad futura. Este valor debe ser 0 (cero).|  
|`guidScheme`|Entidad que agrega la referencia. Este campo puede tener uno de los valores siguientes:<br /><br /> -FUSION_REFCOUNT_MSI_GUID: una aplicación que se instaló mediante el Microsoft Windows Installer hace referencia al ensamblado. El campo `szIdentifier` está establecido en `MSI`y el campo `szNonCanonicalData` se establece en `Windows Installer`. Este esquema se utiliza para los ensamblados en paralelo de Windows.<br />-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: una aplicación que aparece en la interfaz **Agregar o quitar programas** hace referencia al ensamblado. El campo `szIdentifier` proporciona el token que registra la aplicación con la interfaz **Agregar o quitar programas** .<br />-FUSION_REFCOUNT_FILEPATH_GUID: una aplicación que representa un archivo en el sistema de archivos hace referencia al ensamblado. En el campo `szIdentifier` se proporciona la ruta de acceso a este archivo.<br />-FUSION_REFCOUNT_OPAQUE_STRING_GUID: una aplicación que representa solo una cadena opaca hace referencia al ensamblado. El campo `szIdentifier` proporciona esta cadena opaca. La caché global de ensamblados no comprueba la existencia de referencias opacas al quitar este valor.<br />-FUSION_REFCOUNT_OSINSTALL_GUID: este valor está reservado.|  
|`szIdentifier`|Cadena única que identifica la aplicación que ha instalado el ensamblado en la caché global de ensamblados. Su valor depende del valor del campo `guidScheme`.|  
|`szNonCanonicalData`|Cadena que solo entiende la entidad que agrega la referencia. La caché global de ensamblados almacena esta cadena, pero no la utiliza.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de fusión](fusion-structures.md)
- [Caché global de ensamblados](../../app-domains/gac.md)
