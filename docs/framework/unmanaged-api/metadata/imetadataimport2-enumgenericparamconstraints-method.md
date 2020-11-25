---
title: IMetaDataImport2::EnumGenericParamConstraints (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParamConstraints
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type:
- apiref
ms.openlocfilehash: 27c3ec349cf6c83f6783e252e6c5af5e99fa4b37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702841"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a>IMetaDataImport2::EnumGenericParamConstraints (Método)

Obtiene un enumerador para una matriz de restricciones de parámetros genéricos asociada al parámetro genérico representado por el token especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `phEnum`  
 [in, out] Puntero al enumerador.  
  
 `tk`  
 de   Token que representa el parámetro genérico cuyas restricciones se van a enumerar.  
  
 `rGenericParamConstraints`  
 enuncia Matriz de restricciones de parámetro genérico que se va a enumerar.  
  
 `cMax`  
 de   Número máximo solicitado de tokens que se van a colocar en `rGenericParamConstraints` .  
  
 `pcGenericParamConstraints`  
 enuncia Puntero al número de tokens colocados en `rGenericParamConstraints` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParameterConstraints` se devolvió correctamente.|  
|`S_FALSE`|`phEnum` no tiene elementos de miembro. En este caso, `pcGenericParameterConstraints` se establece en 0 (cero).|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
