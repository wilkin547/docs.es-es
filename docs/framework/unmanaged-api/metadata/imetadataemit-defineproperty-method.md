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
ms.openlocfilehash: f11b374ed0ecbfc137c43fb641ae691237604691
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431524"
---
# <a name="imetadataemitdefineproperty-method"></a>IMetaDataEmit::DefineProperty (Método)
Crea una definición de propiedad para el tipo especificado, con los descriptores de acceso `get` y `set` método especificados, y obtiene un token para esa definición de propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="parameters"></a>Parámetros  
 `td`  
 de Token de la clase o interfaz en la que se define la propiedad.  
  
 `szProperty`  
 de Nombre de la propiedad.  
  
 `dwPropFlags`  
 de Marcas de propiedad.  
  
 `pvSig`  
 de Firma de la propiedad.  
  
 `cbSig`  
 de Recuento de bytes de `pvSig`.  
  
 `dwCPlusTypeFlag`  
 de Tipo del valor predeterminado de la propiedad.  
  
 `pValue`  
 de Valor predeterminado de la propiedad.  
  
 `cchValue`  
 de Recuento de caracteres (Unicode) de `pValue`.  
  
 `mdSetter`  
 de El método que establece el valor de propiedad.  
  
 `mdGetter`  
 de Método que obtiene el valor de propiedad.  
  
 `rmdOtherMethods[]`  
 de Matriz de otros métodos asociados a la propiedad. Finalice la matriz con un `mdTokenNil`.  
  
 `pmdProp`  
 enuncia El token de `mdProperty` asignado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
