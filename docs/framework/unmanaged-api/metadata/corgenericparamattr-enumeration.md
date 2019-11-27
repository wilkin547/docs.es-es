---
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
ms.openlocfilehash: e4abf876681d5b04555c9f030a94b722874e326e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450284"
---
# <a name="corgenericparamattr-enumeration"></a>CorGenericParamAttr (Enumeración)
Contiene valores que describen los parámetros de <xref:System.Type> para los tipos genéricos, tal y como se usan en las llamadas a [IMetaDataEmit2::D efinegenericparam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).  
  
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
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`gpVarianceMask`|La varianza de parámetros solo se aplica a los parámetros genéricos para interfaces y delegados.|  
|`gpNonVariant`|Indica la ausencia de varianza.|  
|`gpCovariant`|Indica covarianza.|  
|`gpContravariant`|Indica la contravarianza.|  
|`gpSpecialConstraintMask`|Las restricciones especiales se pueden aplicar a cualquier <xref:System.Type> parámetro.|  
|`gpNoSpecialConstraint`|Indica que no se aplica ninguna restricción al parámetro <xref:System.Type>.|  
|`gpReferenceTypeConstraint`|Indica que el parámetro <xref:System.Type> debe ser un tipo de referencia.|  
|`gpNotNullableValueTypeConstraint`|Indica que el parámetro <xref:System.Type> debe ser un tipo de valor que no puede ser un valor null.|  
|`gpDefaultConstructorConstraint`|Indica que el parámetro <xref:System.Type> debe tener un constructor público predeterminado que no tome ningún parámetro.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
