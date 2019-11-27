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
 de Un token ParamDef que representa el parámetro para el que se van a devolver los metadatos.  
  
 `pmd`  
 enuncia Un puntero a un token MethodDef que representa el método que toma el parámetro.  
  
 `pulSequence`  
 enuncia Posición ordinal del parámetro en la lista de argumentos del método.  
  
 `szName`  
 enuncia Búfer que contiene el nombre del parámetro.  
  
 `cchName`  
 de Tamaño solicitado en caracteres anchos de `szName`.  
  
 `pchName`  
 enuncia Tamaño devuelto en caracteres anchos de `szName`.  
  
 `pdwAttr`  
 enuncia Un puntero a cualquier marcador de atributo asociado al parámetro. Se trata de una máscara de máscara de valores `CorParamAttr`.  
  
 `pdwCPlusTypeFlag`  
 enuncia Un puntero a una marca que especifica que el parámetro es un <xref:System.ValueType>.  
  
 `ppValue`  
 enuncia Puntero a una cadena constante devuelta por el parámetro.  
  
 `pcchValue`  
 enuncia Tamaño de `ppValue` en caracteres anchos o cero si `ppValue` no contiene una cadena.  
  
## <a name="remarks"></a>Comentarios

Los valores de secuencia de `pulSequence` comienzan por 1 para los parámetros. Un valor devuelto tiene un número de secuencia de 0.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
