---
title: ASSEMBLYMETADATA (Estructura)
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83f6190872ecf4435688f3b7c82a61f5f15d9f62
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443331"
---
# <a name="assemblymetadata-structure"></a>ASSEMBLYMETADATA (Estructura)
Contiene información sobre el ensamblado que se hace referencia, incluyendo su versión y su nivel de compatibilidad con configuraciones regionales, procesadores y sistemas operativos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`usMajorVersion`|El número de versión principal del ensamblado que se hace referencia. Este valor no puede ser cero. Si todos los bits de `usMajorVersion` están configurados, no se especifica la versión principal.|  
|`usMinorVersion`|El número de versión secundaria del ensamblado que se hace referencia. Este valor no puede ser cero. Si todos los bits de `usMinorVersion` están configurados, no se especifica la versión secundaria.|  
|`usBuildNumber`|El número de compilación del ensamblado que se hace referencia. Este valor no puede ser cero. Si todos los bits de `usBuildNumber` están configurados, no se especifica el número de compilación.|  
|`usRevisionNumber`|El número de revisión del ensamblado que se hace referencia. Este valor no puede ser cero. Si todos los bits de `usRevisionNumber` están configurados, no se especifica el número de revisión.|  
|`szLocale`|Una lista de nombres de configuración regional que cumplen la especificación RFC1766, separada por punto y coma, especificar las configuraciones regionales admitidas por el ensamblado que se hace referencia. Un valor null indica la independencia de la configuración regional. **Nota:** en .NET Framework versión 1.0 no se puede especificar más de una configuración regional.|  
|`cbLocale`|El tamaño en caracteres anchos de `szLocale`.|  
|`rdwProcessor`|Una matriz de identificadores, tal como se define en Winnt.h, para los tipos de procesador que son compatibles con el ensamblado que se hace referencia. Un valor NULL indica la dependencia del procesador.|  
|`ulProcessor`|La longitud de la `rdwProcessor` matriz.|  
|`rOS`|Una matriz de [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instancias especificando los sistemas operativos que son compatibles con el ensamblado que se hace referencia. Un valor NULL indica la dependencia del sistema operativo.|  
|`ulOS`|La longitud de la `rOS` matriz.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [OSINFO (estructura)](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
