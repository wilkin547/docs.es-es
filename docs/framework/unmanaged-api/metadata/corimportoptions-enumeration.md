---
description: 'Más información sobre: enumeración Corimportoptions ('
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
ms.openlocfilehash: b942ed3f5b1b3c400b4f901e3dd3c4364e1d588c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784449"
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
  
## <a name="members"></a>Members  
  
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

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
