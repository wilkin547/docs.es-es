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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbb3ac150ebfe9fe3698427d8bb2bfb3e3347c07
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796457"
---
# <a name="ienumidentity_attribute-interface"></a>IEnumIDENTITY_ATTRIBUTE (Interfaz)
Actúa como un enumerador para los atributos del objeto de código en el ámbito actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|Obtiene un puntero de interfaz a un `IEnumIDENTITY_ATTRIBUTE` nuevo que contiene los mismos miembros que `IEnumIDENTITY_ATTRIBUTE`este.|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|Escribe los datos contenidos en los elementos de este `IEnumIDENTITY_ATTRIBUTE` en el búfer de datos especificado.|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|Obtiene el número especificado de atributos, comenzando en la posición actual.|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|Mueve el puntero de instrucción al principio de este `IEnumIDENTITY_ATTRIBUTE`.|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|Mueve el puntero de instrucción hacia delante el número especificado de elementos, comenzando en la posición actual.|  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Isolation. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
