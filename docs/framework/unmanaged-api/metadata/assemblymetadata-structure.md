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
ms.openlocfilehash: 24ec1f7d553a59425f7eb02af8e91010d940eb07
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444258"
---
# <a name="assemblymetadata-structure"></a>ASSEMBLYMETADATA (Estructura)
Contiene información acerca del ensamblado al que se hace referencia, incluida su versión y su nivel de compatibilidad con configuraciones regionales, procesadores y sistemas operativos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`usMajorVersion`|Número de versión principal del ensamblado al que se hace referencia. Este valor no puede ser cero. Si se establecen todos los bits de `usMajorVersion`, no se especifica la versión principal.|  
|`usMinorVersion`|Número de versión secundaria del ensamblado al que se hace referencia. Este valor no puede ser cero. Si se establecen todos los bits de `usMinorVersion`, no se especifica la versión secundaria.|  
|`usBuildNumber`|Número de compilación del ensamblado al que se hace referencia. Este valor no puede ser cero. Si se establecen todos los bits de `usBuildNumber`, no se especifica el número de compilación.|  
|`usRevisionNumber`|El número de revisión del ensamblado al que se hace referencia. Este valor no puede ser cero. Si se establecen todos los bits de `usRevisionNumber`, no se especifica el número de revisión.|  
|`szLocale`|Una lista de nombres de configuración regional que se ajustan a la especificación de RFC1766, separadas por punto y coma, que especifican las configuraciones regionales que admite el ensamblado al que se hace referencia. Un valor null indica la independencia de la configuración regional. **Nota:**  En la versión .NET Framework 1,0 no puede especificar más de una configuración regional.|  
|`cbLocale`|Tamaño en caracteres anchos de `szLocale`.|  
|`rdwProcessor`|Matriz de identificadores, tal y como se define en Winnt. h, para los tipos de procesador admitidos por el ensamblado al que se hace referencia. Un valor NULL indica la independencia del procesador.|  
|`ulProcessor`|Longitud de la matriz de `rdwProcessor`.|  
|`rOS`|Una matriz de instancias de [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) que especifican los sistemas operativos admitidos por el ensamblado al que se hace referencia. Un valor NULL indica la independencia del sistema operativo.|  
|`ulOS`|Longitud de la matriz de `rOS`.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [OSINFO (estructura)](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
