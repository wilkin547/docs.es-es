---
title: "IMetaDataImport::GetPropertyProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPropertyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d838f43b500ac3dd0c3b44d9d84dd9fc039c6e16
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parámetros  
 `prop`  
 [in] Un token que representa la propiedad que se va a devolver los metadatos.  
  
 `pClass`  
 [out] Un puntero al token de TypeDef que representa el tipo que implementa la propiedad.  
  
 `szProperty`  
 [out] Un búfer para almacenar el nombre de propiedad.  
  
 `cchProperty`  
 [in] El tamaño en caracteres anchos de `szProperty`.  
  
 `pchProperty`  
 [out] El número de caracteres anchos devueltos en `szProperty`.  
  
 `pdwPropFlags`  
 [out] Puntero a cualquier indicador de atributo aplicado a la propiedad. Este valor es una máscara de bits de la [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeración.  
  
 `ppvSig`  
 [out] Un puntero a la firma de metadatos de la propiedad.  
  
 `pbSig`  
 [out] El número de bytes devueltos en `ppvSig`.  
  
 `pdwCPlusTypeFlag`  
 [out] Una marca que especifica el tipo de la constante que es el valor predeterminado de la propiedad. Este valor está entre el CorElementType (enumeración).  
  
 `ppDefaultValue`  
 [out] Un puntero que indica los bytes que almacenan el valor predeterminado de esta propiedad.  
  
 `pcchDefaultValue`  
 [out] El tamaño en caracteres anchos de `ppDefaultValue`si `pdwCPlusTypeFlag` es ELEMENT_TYPE_STRING; en caso contrario, este valor no es relevante. En ese caso, la longitud de `ppDefaultValue` se deduzcan del tipo especificado por `pdwCPlusTypeFlag`.  
  
 `pmdSetter`  
 [out] Un puntero al token de MethodDef que representa el método de descriptor de acceso set para la propiedad.  
  
 `pmdGetter`  
 [out] Un puntero al token de MethodDef que representa el método de descriptor de acceso get de la propiedad.  
  
 `rmdOtherMethod`  
 [out] Una matriz de los tokens de MethodDef que representan los otros métodos asociados a la propiedad.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rmdOtherMethod`. Si no se proporciona una matriz lo suficientemente grande como para contener todos los métodos, se omiten sin ninguna advertencia previa.  
  
 `pcOtherMethod`  
 [out] El número de tokens de MethodDef devueltos en `rmdOtherMethod`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
