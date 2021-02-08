---
description: 'Más información sobre: enumeración CorGenericParamAttr ('
title: CorGenericParamAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
ms.openlocfilehash: 8fe8cb20834ecbc5477bbe8b01bf77d6b1af0eea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784462"
---
# <a name="corgenericparamattr-enumeration"></a>CorGenericParamAttr (Enumeración)

Contiene valores que describen los <xref:System.Type> parámetros de los tipos genéricos, tal y como se usan en las llamadas a [IMetaDataEmit2::D efinegenericparam](imetadataemit2-definegenericparam-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`gpVarianceMask`|La varianza de parámetros solo se aplica a los parámetros genéricos para interfaces y delegados.|  
|`gpNonVariant`|Indica la ausencia de varianza.|  
|`gpCovariant`|Indica covarianza.|  
|`gpContravariant`|Indica la contravarianza.|  
|`gpSpecialConstraintMask`|Las restricciones especiales se pueden aplicar a cualquier <xref:System.Type> parámetro.|  
|`gpNoSpecialConstraint`|Indica que no se aplica ninguna restricción al <xref:System.Type> parámetro.|  
|`gpReferenceTypeConstraint`|Indica que el <xref:System.Type> parámetro debe ser un tipo de referencia.|  
|`gpNotNullableValueTypeConstraint`|Indica que el <xref:System.Type> parámetro debe ser un tipo de valor que no puede ser un valor null.|  
|`gpDefaultConstructorConstraint`|Indica que el <xref:System.Type> parámetro debe tener un constructor público predeterminado que no tome ningún parámetro.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
