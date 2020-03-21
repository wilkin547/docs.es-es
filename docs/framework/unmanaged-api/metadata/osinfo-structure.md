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
ms.openlocfilehash: 048fe687e4d979576896f5310bddc855b40bb695
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175231"
---
# <a name="osinfo-structure"></a>OSINFO (Estructura)
Contiene detalles sobre el sistema operativo de un ensamblado o módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`dwOSPlatformId`|Uno de los valores de identificador `GetVersionEx`definidos por la función de plataforma Microsoft Windows . Se admiten los valores siguientes:<br /><br /> - VER_PLATFORM_WIN32s, o 0x0000, para especificar Microsoft Windows 3.1.<br />- VER_PLATFORM_WIN32_WINDOWS, o 0x0001, para especificar Windows 95, Windows 98 o sistemas operativos descendientes de ellos.<br />- VER_PLATFORM_WIN32_NT, o 0x0002, para especificar Windows NT o sistemas operativos descendientes de él.|  
|`dwOSMajorVersion`|La versión principal del sistema operativo o un valor NULL para indicar cualquier versión.|  
|`dwOSMinorVersion`|La versión secundaria del sistema operativo o un valor NULL para indicar cualquier versión.|  
  
## <a name="remarks"></a>Observaciones  
 `OSINFO`se basa `OSVERSIONINFOEX` en la estructura que se utiliza `GetVersionEx`en las llamadas a la función de plataforma Microsoft Windows. Esta estructura es utilizada por la estructura ASSEMBLYMETADATA para indicar su compatibilidad con el sistema operativo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [IMetaDataAssemblyEmit (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
