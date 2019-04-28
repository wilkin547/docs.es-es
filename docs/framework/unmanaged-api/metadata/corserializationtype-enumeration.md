---
title: CorSerializationType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorSerializationType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSerializationType
helpviewer_keywords:
- CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15b1f6be2dac6bc7566852791ac22e495949521c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992646"
---
# <a name="corserializationtype-enumeration"></a>CorSerializationType (Enumeración)
Especifica cómo se serializa un objeto por common language runtime.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|La serialización del objeto es indefinida.|  
|`SERIALIZATION_TYPE_BOOLEAN`|El objeto se serializa como un tipo booleano|  
|`SERIALIZATION_TYPE_CHAR`|Objeto se serializa como un tipo de carácter.|  
|`SERIALIZATION_TYPE_I1`|Objeto se serializa como un entero de 1 byte con signo.|  
|`SERIALIZATION_TYPE_U1`|Objeto se serializa como un entero de 1 byte sin signo.|  
|`SERIALIZATION_TYPE_I2`|Objeto se serializa como un entero de 2 bytes con signo.|  
|`SERIALIZATION_TYPE_U2`|Objeto se serializa como un entero de 2 bytes sin signo.|  
|`SERIALIZATION_TYPE_I4`|Objeto se serializa como un entero de 4 bytes con signo.|  
|`SERIALIZATION_TYPE_U4`|Objeto se serializa como un entero de 4 bytes sin signo.|  
|`SERIALIZATION_TYPE_I8`|Objeto se serializa como un entero de 8 bytes con signo.|  
|`SERIALIZATION_TYPE_U8`|Objeto se serializa como un entero de 8 bytes sin signo.|  
|`SERIALIZATION_TYPE_R4`|Objeto se serializa como un punto flotante de 4 bytes.|  
|`SERIALIZATION_TYPE_R8`|Objeto se serializa como un punto flotante de 8 bytes.|  
|`SERIALIZATION_TYPE_STRING`|Objeto se serializa como un tipo System.String.|  
|`SERIALIZATION_TYPE_SZARRAY`|El objeto se serializa como una sola dimensión, matriz de límite inferior cero.|  
|`SERIALIZATION_TYPE_TYPE`|Objeto se serializa como un tipo genérico.|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|Objeto se serializa como un objeto etiquetado.|  
|`SERIALIZATION_TYPE_FIELD`|Objeto se serializa como un campo.|  
|`SERIALIZATION_TYPE_PROPERTY`|Objeto se serializa como una propiedad.|  
|`SERIALIZATION_TYPE_ENUM`|Objeto se serializa como una enumeración.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
