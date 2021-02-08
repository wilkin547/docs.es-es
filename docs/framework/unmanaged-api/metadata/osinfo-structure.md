---
description: 'Más información sobre: OSINFO (estructura)'
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
ms.openlocfilehash: 5027ef5cf4137aa1e781134b325407e1251fdd31
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799114"
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`dwOSPlatformId`|Uno de los valores de identificador definidos por la función de la plataforma Microsoft Windows `GetVersionEx` . Se admiten los valores siguientes:<br /><br /> -VER_PLATFORM_WIN32s, o 0x0000, para especificar Microsoft Windows 3,1.<br />-VER_PLATFORM_WIN32_WINDOWS, o 0x0001, para especificar los sistemas operativos Windows 95, Windows 98 o que descienden de ellos.<br />-VER_PLATFORM_WIN32_NT, o 0x0002, para especificar los sistemas operativos Windows NT o que descienden de él.|  
|`dwOSMajorVersion`|La versión principal del sistema operativo o un valor NULL para indicar cualquier versión.|  
|`dwOSMinorVersion`|La versión secundaria del sistema operativo o un valor NULL para indicar cualquier versión.|  
  
## <a name="remarks"></a>Observaciones  

 `OSINFO` se basa en la `OSVERSIONINFOEX` estructura que se utiliza en las llamadas a la función de la plataforma Microsoft Windows `GetVersionEx` . La estructura ASSEMBLYMETADATA (usa esta estructura para indicar su compatibilidad con el sistema operativo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de metadatos](metadata-structures.md)
- [IMetaDataAssemblyEmit (Interfaz)](imetadataassemblyemit-interface.md)
