---
title: CorImportOptions (Enumeración)
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2f71a277484adbbfe3628222c635528cdab03e6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156135"
---
# <a name="corimportoptions-enumeration"></a>CorImportOptions (Enumeración)
Contiene valores de marca que controlan el comportamiento durante la importación de un ensamblado fuera del ámbito actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`MDImportOptionDefault`|Indica el comportamiento predeterminado, que se usa para omitir los registros eliminados.|  
|`MDImportOptionAll`|Indica que se deben enumerar todos los metadatos.|  
|`MDImportOptionAllTypeDefs`|Indica que se deben enumerar todas las definiciones de tipos, incluidos los eliminados.|  
|`MDImportOptionAllMethodDefs`|Indica que se deben enumerar todos los MethodDefs, incluyendo los eliminados.|  
|`MDImportOptionAllFieldDefs`|Indica que se deben enumerar todos los FieldDefs, incluyendo los eliminados.|  
|`MDImportOptionAllProperties`|Indica que se deben enumerar todos los PropertyDefs, incluyendo los eliminados.|  
|`MDImportOptionAllEvents`|Indica que se deben enumerar todos los EventDefs, incluyendo los eliminados.|  
|`MDImportOptionAllCustomAttributes`|Indica que se deben enumerar todos los atributos personalizados, incluyendo los eliminados.|  
|`MDImportOptionAllExportedTypes`|Indica que se deben enumerar todos los tipos exportados, incluidos los eliminados.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
