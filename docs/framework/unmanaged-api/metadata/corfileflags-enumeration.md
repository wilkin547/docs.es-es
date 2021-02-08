---
description: 'Más información sobre: enumeración CorFileFlags ('
title: CorFileFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
ms.openlocfilehash: 8ffad9bad9c656a10c2c556f5e06f9d510ccb45a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784488"
---
# <a name="corfileflags-enumeration"></a>CorFileFlags (Enumeración)

Contiene valores que describen el tipo de archivo definido en una llamada a [IMetaDataAssemblyEmit::D efinefile](imetadataassemblyemit-definefile-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`ffContainsMetaData`|Indica que el archivo no es un archivo de recursos.|  
|`ffContainsNoMetaData`|Indica que el archivo, posiblemente un archivo de recursos, no contiene metadatos.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
