---
title: IMetaDataImport2::EnumGenericParams (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
ms.openlocfilehash: 6b1a8e66eea6caec9dfc8d99e343c987cefa1b0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702763"
---
# <a name="imetadataimport2enumgenericparams-method"></a>IMetaDataImport2::EnumGenericParams (Método)

Obtiene un enumerador para una matriz de tokens de parámetro genéricos asociados al token de TypeDef o MethodDef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],
   [in]  ULONG            cMax,
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `phEnum`  
 [in, out] Puntero al enumerador.  
  
 `tk`  
 de El token TypeDef o MethodDef cuyos parámetros genéricos se van a enumerar.  
  
 `rGenericParams`  
 enuncia Matriz de parámetros genéricos que se va a enumerar.  
  
 `cMax`  
 de Número máximo solicitado de tokens que se van a colocar en `rGenericParams` .  
  
 `pcGenericParams`  
 enuncia Número devuelto de tokens colocados en `rGenericParams` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParams` se devolvió correctamente.|  
|`S_FALSE`|`phEnum` no tiene elementos de miembro. En este caso, `pcGenericParams` se establece en 0 (cero).|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
