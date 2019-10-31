---
title: IEnumIDENTITY_ATTRIBUTE (Interfaz)
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
ms.openlocfilehash: 7e6bc57fb470a5c12549bb5f9445ecf1551425a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107838"
---
# <a name="ienumidentity_attribute-interface"></a>IEnumIDENTITY_ATTRIBUTE (Interfaz)
Actúa como un enumerador para los atributos del objeto de código en el ámbito actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|Obtiene un puntero de interfaz a un nuevo `IEnumIDENTITY_ATTRIBUTE` que contiene los mismos miembros que este `IEnumIDENTITY_ATTRIBUTE`.|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|Escribe los datos contenidos en los elementos de este `IEnumIDENTITY_ATTRIBUTE` en el búfer de datos especificado.|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|Obtiene el número especificado de atributos, comenzando en la posición actual.|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|Mueve el puntero de instrucción al principio de este `IEnumIDENTITY_ATTRIBUTE`.|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|Mueve el puntero de instrucción hacia delante el número especificado de elementos, comenzando en la posición actual.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Isolation. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
