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
ms.openlocfilehash: 44d1776e2902988353ef4fd58aca20e56203b9da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442849"
---
# <a name="corimportoptions-enumeration"></a>CorImportOptions (Enumeración)
Contiene valores de marca que controlan el comportamiento durante la importación de un ensamblado fuera del ámbito actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`MDImportOptionDefault`|Indica el comportamiento predeterminado, que consiste en omitir los registros eliminados.|  
|`MDImportOptionAll`|Indica que se deben enumerar todos los metadatos.|  
|`MDImportOptionAllTypeDefs`|Indica que se deben enumerar todos los TypeDefs, incluidos los eliminados.|  
|`MDImportOptionAllMethodDefs`|Indica que se deben enumerar todos los MethodDefs, incluidos los eliminados.|  
|`MDImportOptionAllFieldDefs`|Indica que se deben enumerar todos los FieldDefs, incluidos los eliminados.|  
|`MDImportOptionAllProperties`|Indica que se deben enumerar todos los PropertyDefs, incluidos los eliminados.|  
|`MDImportOptionAllEvents`|Indica que se deben enumerar todos los EventDefs, incluidos los eliminados.|  
|`MDImportOptionAllCustomAttributes`|Indica que se deben enumerar todos los atributos personalizados, incluidos los eliminados.|  
|`MDImportOptionAllExportedTypes`|Indica que se deben enumerar todos los tipos exportados, incluidos los eliminados.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
