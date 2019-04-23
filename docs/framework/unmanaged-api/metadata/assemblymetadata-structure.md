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
ms.openlocfilehash: 8f0a9b9c149c86b4d9121275aa858dfdc0cdbac7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195168"
---
# <a name="assemblymetadata-structure"></a>ASSEMBLYMETADATA (Estructura)
Contiene información sobre el ensamblado que se hace referencia, incluidos su versión y su nivel de compatibilidad con configuraciones regionales, procesadores y sistemas operativos.  
  
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
|`szLocale`|Una lista de nombres de configuración regional que cumplen la especificación RFC1766, separada por punto y coma, que se especifican las configuraciones regionales admitidas el ensamblado que se hace referencia. Un valor nulo indica la independencia de la configuración regional. **Nota:**  En .NET Framework versión 1.0 no se puede especificar más de una configuración regional.|  
|`cbLocale`|El tamaño en caracteres anchos de `szLocale`.|  
|`rdwProcessor`|Una matriz de identificadores, como se define en Winnt.h, para los tipos de procesador que son compatibles con el ensamblado que se hace referencia. Un valor NULL indica la dependencia del procesador.|  
|`ulProcessor`|La longitud de la `rdwProcessor` matriz.|  
|`rOS`|Una matriz de [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instancias especificando los sistemas operativos que son compatibles con el ensamblado que se hace referencia. Un valor NULL indica la dependencia del sistema operativo.|  
|`ulOS`|La longitud de la `rOS` matriz.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [OSINFO (estructura)](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
