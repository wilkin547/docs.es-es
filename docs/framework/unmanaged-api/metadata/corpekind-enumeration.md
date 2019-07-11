---
title: CorPEKind (Enumeración)
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0bfe30567bcd8e22a82d401e00b0a6ee50407def
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781667"
---
# <a name="corpekind-enumeration"></a>CorPEKind (Enumeración)
Contiene valores que describen un archivo ejecutable portable (PE), tal como lo devuelve una llamada a [IMetaDataImport2:: GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`peNot`|Indica que no es un archivo PE.|  
|`peILOnly`|Indica que este archivo PE contiene sólo código administrado.|  
|`pe32BitRequired`|Indica que este archivo PE efectúa llamadas a Win32.|  
|`pe32Plus`|Indica que este archivo PE se ejecuta en una plataforma de 64 bits.|  
|`pe32Unmanaged`|Indica que este archivo PE es código nativo.|  
|pe32BitPreferred|Indica que este archivo PE es independiente de la plataforma y prefiere que se cargue en un entorno de 32 bits.|  
  
## <a name="remarks"></a>Comentarios  
 Estos valores se pueden usar en combinaciones bit a bit.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
