---
description: 'Más información sobre: enumeración Corlocalrefpreservation ('
title: CorLocalRefPreservation (Enumeración)
ms.date: 03/30/2017
api_name:
- CorLocalRefPreservation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLocalRefPreservation
helpviewer_keywords:
- CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type:
- apiref
ms.openlocfilehash: afcdf6ce22c5f786e8f728cc1e45ad3ca44e7ef5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784423"
---
# <a name="corlocalrefpreservation-enumeration"></a>CorLocalRefPreservation (Enumeración)

Contiene valores de marca para el tratamiento de referencias locales.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|No conservar ninguna referencia local.|  
|`MDPreserveLocalTypeRef`|Conserva las referencias de tipo local.|  
|`MDPreserveLocalMemberRef`|Conservar las referencias de miembro local.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
