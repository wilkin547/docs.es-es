---
title: CorFileMapping (Enumeración)
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9b3802c9c72ec3a9302e403e55789aab8102cf1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624995"
---
# <a name="corfilemapping-enumeration"></a>CorFileMapping (Enumeración)
Contiene valores que describen el tipo de asignación de archivo que se devuelve de una llamada a la [IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`fmFlat`|El archivo se asigna como un archivo de datos. Es decir, el `SEC_IMAGE` marca no se pasó a Microsoft Win32 `CreateFileMapping` función.|  
|`fmExecutableImage`|El archivo se ha asignado para ejecución, mediante el uso del `LoadLibrary` función o el `CreateFileMapping` funcionando con el `SEC_IMAGE` marca.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [GetFileMapping (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
