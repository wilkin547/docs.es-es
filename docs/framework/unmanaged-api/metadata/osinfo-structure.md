---
title: OSINFO (Estructura)
ms.date: 03/30/2017
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a36cd3c5fb638799a735e4b4a1a98959500300b5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761595"
---
# <a name="osinfo-structure"></a>OSINFO (Estructura)
Contiene detalles sobre el sistema operativo para un ensamblado o módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`dwOSPlatformId`|Uno de los valores de identificador definidos por la función de la plataforma Microsoft Windows `GetVersionEx`. Se admiten los siguientes valores:<br /><br /> -VER_PLATFORM_WIN32s, o 0 x 0000, para especificar Microsoft Windows 3.1.<br />-VER_PLATFORM_WIN32_WINDOWS, o 0 x 0001, para especificar Windows 95, Windows 98 o sistemas operativos que se hereda de ellos.<br />-VER_PLATFORM_WIN32_NT, o 0 x 0010, para especificar Windows NT o sistemas operativos que se hereda de él.|  
|`dwOSMajorVersion`|La versión principal del sistema operativo o un valor NULL para indicar cualquier versión.|  
|`dwOSMinorVersion`|La versión secundaria del sistema operativo o un valor NULL para indicar cualquier versión.|  
  
## <a name="remarks"></a>Comentarios  
 `OSINFO` se basa en el `OSVERSIONINFOEX` estructura que es utilizado en las llamadas a la función de la plataforma Microsoft Windows `GetVersionEx`. Esta estructura se usa por ASSEMBLYMETADATA (estructura) para indicar su compatibilidad de sistema operativo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
