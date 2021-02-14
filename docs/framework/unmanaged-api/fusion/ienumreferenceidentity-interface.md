---
description: 'Más información acerca de: interfaz Ienumreferenceidentity ('
title: IEnumReferenceIdentity (Interfaz)
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
ms.openlocfilehash: a7f17793fd737b5153c27dae59fb2aa87b46cf48
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100465306"
---
# <a name="ienumreferenceidentity-interface"></a>IEnumReferenceIdentity (Interfaz)

Actúa como un enumerador para una colección de `IReferenceIdentity` objetos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|Obtiene un puntero de interfaz a un nuevo `IEnumReferenceIdentity` que contiene los mismos miembros que este `IEnumReferenceIdentity` .|  
|`IEnumReferenceIdentity::Next`|Obtiene el número especificado de `IReferenceIdentity` objetos, empezando en la posición actual.|  
|`IEnumReferenceIdentity::Reset`|Mueve el puntero de instrucción al principio de este `IEnumReferenceIdentity` .|  
|`IEnumReferenceIdentity::Skip`|Mueve el puntero de instrucción hacia delante el número especificado de elementos, comenzando en la posición actual.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Isolation. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de Fusion](fusion-interfaces.md)
- [IReferenceIdentity (Interfaz)](ireferenceidentity-interface.md)
