---
description: 'Más información sobre: enumeración COUNINITIEE ('
title: COUNINITIEE (Enumeración)
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
ms.openlocfilehash: 893ab96851e9c762a888f3c4cac98b486a0b4614
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707239"
---
# <a name="couninitiee-enumeration"></a>COUNINITIEE (Enumeración)

Especifica las constantes utilizadas por [CoUninitializeEE (](../hosting/couninitializeee-function.md) al inicializar el Common Language Runtime.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|Indica el modo de no inicialización predeterminado.|  
|`COUNINITEE_DLL`|Indica el modo de anulación de la carga de un ensamblado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
