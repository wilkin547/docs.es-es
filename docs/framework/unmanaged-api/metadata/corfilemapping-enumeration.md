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
ms.openlocfilehash: 63e27a62e176a92b03c10b59a55d9da3192918f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726123"
---
# <a name="corfilemapping-enumeration"></a>CorFileMapping (Enumeración)

Contiene valores que describen el tipo de asignación de archivos que se devuelve de una llamada al método [IMetaDataInfo:: getfilemapping (](imetadatainfo-getfilemapping-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`fmFlat`|El archivo se asigna como un archivo de datos. Es decir, la `SEC_IMAGE` marca no se pasó a la función de Microsoft Win32 `CreateFileMapping` .|  
|`fmExecutableImage`|El archivo se asigna para su ejecución mediante la `LoadLibrary` función o la `CreateFileMapping` función con la `SEC_IMAGE` marca.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
- [Método GetFileMapping](imetadatainfo-getfilemapping-method.md)
