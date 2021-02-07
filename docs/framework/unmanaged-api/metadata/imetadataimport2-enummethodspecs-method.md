---
description: 'Más información sobre: IMetaDataImport2:: Enummethodspecs ((método)'
title: IMetaDataImport2::EnumMethodSpecs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 19fff1d78599d968bb1fd0ab27b0f71e41fae20b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677527"
---
# <a name="imetadataimport2enummethodspecs-method"></a>IMetaDataImport2::EnumMethodSpecs (Método)

Obtiene un enumerador para una matriz de tokens MethodSpec asociados al token MethodDef o MemberRef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a>Parámetros  

 `phEnum`  
 [in, out] Puntero al enumerador de `rMethodSpecs` .  
  
 `tk`  
 de El token MemberRef o MethodDef que representa el método cuyos tokens MethodSpec se van a enumerar. Si el valor de `tk` es 0 (cero), se enumerarán todos los tokens MethodSpec en el ámbito.  
  
 `rMethodSpecs`  
 enuncia Matriz de tokens MethodSpec que se va a enumerar.  
  
 `cMax`  
 de Número máximo solicitado de tokens que se van a colocar en `rMethodSpecs` .  
  
 `pcMethodSpecs`  
 enuncia Número devuelto de tokens colocados en `rMethodSpecs` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs` se devolvió correctamente.|  
|`S_FALSE`|`phEnum` no tiene elementos de miembro. En este caso, `pcMethodSpecs` se establece en 0 (cero).|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
