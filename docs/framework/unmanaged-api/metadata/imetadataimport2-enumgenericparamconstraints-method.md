---
description: 'Más información sobre: IMetaDataImport2:: Enumgenericparamconstraints ((método)'
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
ms.openlocfilehash: d7ee44059796a943411750b66f5b45034f871a0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677553"
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
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
