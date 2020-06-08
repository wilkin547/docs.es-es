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
ms.openlocfilehash: ab9d7eb6f5760b43fe805443bbe1ea4a95c72069
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501071"
---
# <a name="osinfo-structure"></a>OSINFO (Estructura)
Contiene detalles sobre el sistema operativo de un ensamblado o un módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`dwOSPlatformId`|Uno de los valores de identificador definidos por la función de la plataforma Microsoft Windows `GetVersionEx` . Se admiten los valores siguientes:<br /><br /> -VER_PLATFORM_WIN32s, o 0x0000, para especificar Microsoft Windows 3,1.<br />-VER_PLATFORM_WIN32_WINDOWS, o 0x0001, para especificar los sistemas operativos Windows 95, Windows 98 o que descienden de ellos.<br />-VER_PLATFORM_WIN32_NT, o 0x0002, para especificar los sistemas operativos Windows NT o que descienden de él.|  
|`dwOSMajorVersion`|La versión principal del sistema operativo o un valor NULL para indicar cualquier versión.|  
|`dwOSMinorVersion`|La versión secundaria del sistema operativo o un valor NULL para indicar cualquier versión.|  
  
## <a name="remarks"></a>Comentarios  
 `OSINFO`se basa en la `OSVERSIONINFOEX` estructura que se utiliza en las llamadas a la función de la plataforma Microsoft Windows `GetVersionEx` . La estructura ASSEMBLYMETADATA (usa esta estructura para indicar su compatibilidad con el sistema operativo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Estructuras de metadatos](metadata-structures.md)
- [IMetaDataAssemblyEmit (Interfaz)](imetadataassemblyemit-interface.md)
