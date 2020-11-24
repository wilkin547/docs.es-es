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
ms.openlocfilehash: 001be0c5e8897bacf76d2a044fb9400768473052
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673546"
---
# <a name="corpekind-enumeration"></a>CorPEKind (Enumeración)

Contiene valores que describen un archivo portable ejecutable (PE), tal y como se devuelve de una llamada a [IMetaDataImport2:: getpekind (](imetadataimport2-getpekind-method.md).  
  
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
  
|Miembro|Descripción|  
|------------|-----------------|  
|`peNot`|Indica que este no es un archivo PE.|  
|`peILOnly`|Indica que este archivo PE contiene solo código administrado.|  
|`pe32BitRequired`|Indica que este archivo PE realiza llamadas a Win32.|  
|`pe32Plus`|Indica que este archivo PE se ejecuta en una plataforma de 64 bits.|  
|`pe32Unmanaged`|Indica que este archivo PE es código nativo.|  
|pe32BitPreferred|Indica que este archivo PE es independiente de la plataforma y prefiere que se cargue en un entorno de 32 bits.|  
  
## <a name="remarks"></a>Comentarios  

 Estos valores se pueden usar en combinaciones bit a bit.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
