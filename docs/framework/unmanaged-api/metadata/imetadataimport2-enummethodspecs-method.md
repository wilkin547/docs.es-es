---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c2122c06c6e4f1137173f02e37fb0982864e7ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimport2enummethodspecs-method"></a>IMetaDataImport2::EnumMethodSpecs (Método)
Obtiene un enumerador para una matriz de símbolos (tokens) de MethodSpec asociada al MethodDef o MemberRef especificado (token).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
#### <a name="parameters"></a>Parámetros  
 `phEnum`  
 [entrada, salida] Un puntero al enumerador para `rMethodSpecs`.  
  
 `tk`  
 [in] El token MemberRef o MethodDef que representa el método cuyos símbolos (tokens) MethodSpec se van a enumerar. Si el valor de `tk` es 0 (cero), se enumerarán todos los tokens de MethodSpec en el ámbito.  
  
 `rMethodSpecs`  
 [out] Matriz de símbolos (tokens) de MethodSpec a enumerar.  
  
 `cMax`  
 [in] El número máximo solicitado de símbolos (tokens) para colocar en `rMethodSpecs`.  
  
 `pcMethodSpecs`  
 [out] El número devuelto de símbolos (tokens) se coloca en `rMethodSpecs`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs` se devolvió correctamente.|  
|`S_FALSE`|`phEnum` no tiene ningún elemento de miembro. En este caso, `pcMethodSpecs` se establece en 0 (cero).|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
