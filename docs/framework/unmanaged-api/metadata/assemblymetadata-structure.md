---
description: 'Más información acerca de: estructura ASSEMBLYMETADATA ('
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
ms.openlocfilehash: 6fc9c03bea3b1413cd3a8421746137e37d43bd90
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678944"
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`usMajorVersion`|Número de versión principal del ensamblado al que se hace referencia. Este valor no puede ser cero. Si se establecen todos los bits de `usMajorVersion` , no se especifica la versión principal.|  
|`usMinorVersion`|Número de versión secundaria del ensamblado al que se hace referencia. Este valor no puede ser cero. Si se establecen todos los bits de `usMinorVersion` , no se especifica la versión secundaria.|  
|`usBuildNumber`|Número de compilación del ensamblado al que se hace referencia. Este valor no puede ser cero. Si se establecen todos los bits de `usBuildNumber` , no se especifica el número de compilación.|  
|`usRevisionNumber`|El número de revisión del ensamblado al que se hace referencia. Este valor no puede ser cero. Si se establecen todos los bits de `usRevisionNumber` , no se especifica el número de revisión.|  
|`szLocale`|Una lista de nombres de configuración regional que se ajustan a la especificación de RFC1766, separadas por punto y coma, que especifican las configuraciones regionales que admite el ensamblado al que se hace referencia. Un valor null indica la independencia de la configuración regional. **Nota:**  En la versión .NET Framework 1,0 no puede especificar más de una configuración regional.|  
|`cbLocale`|Tamaño en caracteres anchos de `szLocale` .|  
|`rdwProcessor`|Matriz de identificadores, tal y como se define en Winnt. h, para los tipos de procesador admitidos por el ensamblado al que se hace referencia. Un valor NULL indica la independencia del procesador.|  
|`ulProcessor`|Longitud de la matriz `rdwProcessor`.|  
|`rOS`|Una matriz de instancias de [OSINFO](osinfo-structure.md) que especifican los sistemas operativos admitidos por el ensamblado al que se hace referencia. Un valor NULL indica la independencia del sistema operativo.|  
|`ulOS`|Longitud de la matriz `rOS`.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de metadatos](metadata-structures.md)
- [IMetaDataAssemblyEmit (Interfaz)](imetadataassemblyemit-interface.md)
- [OSINFO (Estructura)](osinfo-structure.md)
