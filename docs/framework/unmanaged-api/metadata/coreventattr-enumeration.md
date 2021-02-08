---
description: 'Más información sobre: enumeración Coreventattr ('
title: CorEventAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorEventAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorEventAttr
helpviewer_keywords:
- CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type:
- apiref
ms.openlocfilehash: 70f05eacf2cc7c7975b9b52d402cceb60bbea426
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784514"
---
# <a name="coreventattr-enumeration"></a>CorEventAttr (Enumeración)

Contiene valores que describen los metadatos de un evento.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`evSpecialName`|Especifica que el evento es especial y que su nombre describe cómo.|  
|`evReservedMask`|Reservado para uso interno por el Common Language Runtime.|  
|`evRTSpecialName`|Especifica que el Common Language Runtime debe comprobar la codificación del nombre del evento.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
