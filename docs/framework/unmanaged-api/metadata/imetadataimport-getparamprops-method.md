---
title: IMetaDataImport::GetParamProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
ms.openlocfilehash: bb73ccdd9eee4b5a655a56b5d6757e0c6003fbc9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437128"
---
# <a name="imetadataimportgetparamprops-method"></a>IMetaDataImport::GetParamProps (Método)
Obtiene los valores de los metadatos del parámetro al que hace referencia el token de ParamDef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `tk`  
 [in] A ParamDef token that represents the parameter to return metadata for.  
  
 `pmd`  
 [out] A pointer to a MethodDef token representing the method that takes the parameter.  
  
 `pulSequence`  
 [out] The ordinal position of the parameter in the method argument list.  
  
 `szName`  
 [out] A buffer to hold the name of the parameter.  
  
 `cchName`  
 [in] The requested size in wide characters of `szName`.  
  
 `pchName`  
 [out] The returned size in wide characters of `szName`.  
  
 `pdwAttr`  
 [out] A pointer to any attribute flags associated with the parameter. This is a bitmask of `CorParamAttr` values.  
  
 `pdwCPlusTypeFlag`  
 [out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.  
  
 `ppValue`  
 [out] A pointer to a constant string returned by the parameter.  
  
 `pcchValue`  
 [out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.  
  
## <a name="remarks"></a>Comentarios

The sequence values in `pulSequence` begin with 1 for parameters. A return value has a sequence number of 0.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Library:** Included as a resource in MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
