---
title: IMetaDataEmit::DefineProperty (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71cdfc6b05288fef020e1aed1870a9a155588d47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543086"
---
# <a name="imetadataemitdefineproperty-method"></a>IMetaDataEmit::DefineProperty (Método)
Crea una definición de propiedad para el tipo especificado, con la especificación `get` y `set` los descriptores de acceso de método y obtiene un token para esa definición de propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineProperty (   
    [in]  mdTypeDef          td,   
    [in]  LPCWSTR            szProperty,   
    [in]  DWORD              dwPropFlags,   
    [in]  PCCOR_SIGNATURE    pvSig,   
    [in]  ULONG              cbSig,   
    [in]  DWORD              dwCPlusTypeFlag,   
    [in]  void const         *pValue,   
    [in]  ULONG              cchValue,   
    [in]  mdMethodDef        mdSetter,   
    [in]  mdMethodDef        mdGetter,   
    [in]  mdMethodDef        rmdOtherMethods[],   
    [out] mdProperty         *pmdProp   
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `td`  
 [in] El token para la clase o interfaz en el que se está definiendo la propiedad.  
  
 `szProperty`  
 [in] El nombre de la propiedad.  
  
 `dwPropFlags`  
 [in] Las marcas de propiedad.  
  
 `pvSig`  
 [in] La firma de la propiedad.  
  
 `cbSig`  
 [in] El recuento de bytes en `pvSig`.  
  
 `dwCPlusTypeFlag`  
 [in] El tipo de valor predeterminado de la propiedad.  
  
 `pValue`  
 [in] El valor predeterminado para la propiedad.  
  
 `cchValue`  
 [in] El recuento de (Unicode) los caracteres de `pValue`.  
  
 `mdSetter`  
 [in] El método que establece el valor de propiedad.  
  
 `mdGetter`  
 [in] El método que obtiene el valor de propiedad.  
  
 `rmdOtherMethods[]`  
 [in] Una matriz de otros métodos asociados a la propiedad. Finalice la matriz con un `mdTokenNil`.  
  
 `pmdProp`  
 [out] El `mdProperty` token asignado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
