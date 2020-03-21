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
ms.openlocfilehash: bf0008ce9429671f0c156df4256bed0b2aaee184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176180"
---
# <a name="corgenericparamattr-enumeration"></a>CorGenericParamAttr (Enumeración)
Contiene valores que <xref:System.Type> describen los parámetros de los tipos genéricos, como se usa en las llamadas a [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).  
  
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
  
|Member|Descripción|  
|------------|-----------------|  
|`gpVarianceMask`|La varianza de parámetros solo se aplica a parámetros genéricos para interfaces y delegados.|  
|`gpNonVariant`|Indica la ausencia de varianza.|  
|`gpCovariant`|Indica covarianza.|  
|`gpContravariant`|Indica contravarianza.|  
|`gpSpecialConstraintMask`|Se pueden aplicar restricciones especiales a cualquier <xref:System.Type> parámetro.|  
|`gpNoSpecialConstraint`|Indica que no se <xref:System.Type> aplica ninguna restricción al parámetro.|  
|`gpReferenceTypeConstraint`|Indica que <xref:System.Type> el parámetro debe ser un tipo de referencia.|  
|`gpNotNullableValueTypeConstraint`|Indica que <xref:System.Type> el parámetro debe ser un tipo de valor que no puede ser un valor nulo.|  
|`gpDefaultConstructorConstraint`|Indica que <xref:System.Type> el parámetro debe tener un constructor público predeterminado que no toma ningún parámetro.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
