---
title: OSINFO (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: OSINFO
api_location: mscoree.dll
api_type: COM
f1_keywords: OSINFO
helpviewer_keywords: OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd30fe7904fa6c0685dd9c39931cc545e4e30583
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="osinfo-structure"></a>OSINFO (Estructura)
Contiene detalles sobre el sistema operativo para un ensamblado o módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`dwOSPlatformId`|Uno de los valores de identificador definidos por la función de la plataforma de Microsoft Windows `GetVersionEx`. Se admiten los siguientes valores:<br /><br /> -VER_PLATFORM_WIN32s, o 0 x 0000, para especificar Microsoft Windows 3.1.<br />-VER_PLATFORM_WIN32_WINDOWS, o 0 x 0001, para especificar Windows 95, Windows 98 o sistemas operativos descendientes de ellos.<br />-VER_PLATFORM_WIN32_NT, o 0 x 0010, para especificar Windows NT o sistemas operativos descendientes de él.|  
|`dwOSMajorVersion`|La versión principal del sistema operativo, o un valor NULL para indicar cualquier versión.|  
|`dwOSMinorVersion`|La versión secundaria del sistema operativo, o un valor NULL para indicar cualquier versión.|  
  
## <a name="remarks"></a>Comentarios  
 `OSINFO`se basa en el `OSVERSIONINFOEX` estructura que es usan en las llamadas a la función de la plataforma de Microsoft Windows `GetVersionEx`. Esta estructura se utiliza por ASSEMBLYMETADATA (estructura) para indicar su compatibilidad de sistema operativo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
