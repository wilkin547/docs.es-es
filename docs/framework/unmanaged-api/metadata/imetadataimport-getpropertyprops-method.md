---
title: IMetaDataImport::GetPropertyProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08bd5beeb9fab1cd5b703c3afc4e82aaf71dbbc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122608"
---
# <a name="imetadataimportgetpropertyprops-method"></a>IMetaDataImport::GetPropertyProps (Método)
Obtiene los metadatos para la propiedad representada por el token especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,   
   [out] LPCWSTR           szProperty,   
   [in]  ULONG             cchProperty,   
   [out] ULONG             *pchProperty,   
   [out] DWORD             *pdwPropFlags,   
   [out] PCCOR_SIGNATURE   *ppvSig,   
   [out] ULONG             *pbSig,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,   
   [out] mdMethodDef       *pmdGetter,   
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,   
   [out] ULONG             *pcOtherMethod   
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `prop`  
 [in] Un token que representa la propiedad para devolver los metadatos.  
  
 `pClass`  
 [out] Un puntero al token de TypeDef que representa el tipo que implementa la propiedad.  
  
 `szProperty`  
 [out] Un búfer para almacenar el nombre de propiedad.  
  
 `cchProperty`  
 [in] El tamaño en caracteres anchos de `szProperty`.  
  
 `pchProperty`  
 [out] El número de caracteres anchos que se devuelven en `szProperty`.  
  
 `pdwPropFlags`  
 [out] Un puntero a cualquier indicador de atributo aplicado a la propiedad. Este valor es una máscara de bits desde el [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeración.  
  
 `ppvSig`  
 [out] Un puntero a la firma de metadatos de la propiedad.  
  
 `pbSig`  
 [out] El número de bytes devuelto en `ppvSig`.  
  
 `pdwCPlusTypeFlag`  
 [out] Una marca que especifica el tipo de la constante que es el valor predeterminado de la propiedad. Este valor es de CorElementType (enumeración).  
  
 `ppDefaultValue`  
 [out] Un puntero a los bytes que almacenar el valor predeterminado para esta propiedad.  
  
 `pcchDefaultValue`  
 [out] El tamaño en caracteres anchos de `ppDefaultValue`si `pdwCPlusTypeFlag` es ELEMENT_TYPE_STRING; en caso contrario, este valor no es relevante. En ese caso, la longitud de `ppDefaultValue` se deduce del tipo especificado por `pdwCPlusTypeFlag`.  
  
 `pmdSetter`  
 [out] Un puntero al token de MethodDef que representa el método de descriptor de acceso set de la propiedad.  
  
 `pmdGetter`  
 [out] Un puntero al token de MethodDef que representa el método de descriptor de acceso get de la propiedad.  
  
 `rmdOtherMethod`  
 [out] Una matriz de los tokens de MethodDef que representan otros métodos asociados a la propiedad.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rmdOtherMethod`. Si no se proporciona una matriz lo suficientemente grande como para contener todos los métodos, se omiten sin previo aviso.  
  
 `pcOtherMethod`  
 [out] El número de tokens de MethodDef devueltos en `rmdOtherMethod`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
