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
ms.openlocfilehash: 7078b2eb98c15b7229132076da8af4691032bb08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
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
|`MDImportOptionAllTypeDefs`|Indica que se deben enumerar todas las definiciones de tipos, incluyendo los eliminados.|  
|`MDImportOptionAllMethodDefs`|Indica que se deben enumerar todos los MethodDefs, incluyendo los eliminados.|  
|`MDImportOptionAllFieldDefs`|Indica que se deben enumerar todos los FieldDefs, incluyendo los eliminados.|  
|`MDImportOptionAllProperties`|Indica que se deben enumerar todos los PropertyDefs, incluyendo los eliminados.|  
|`MDImportOptionAllEvents`|Indica que se deben enumerar todos los EventDefs, incluyendo los eliminados.|  
|`MDImportOptionAllCustomAttributes`|Indica que se deben enumerar todos los atributos personalizados, incluyendo los eliminados.|  
|`MDImportOptionAllExportedTypes`|Indica que se deben enumerar todos los tipos exportados, incluyendo los eliminados.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
