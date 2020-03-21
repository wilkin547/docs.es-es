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
ms.openlocfilehash: eb3ecbf39376e7126b5ec93a26badcbf5076d1db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175790"
---
# <a name="imetadataemitdefineproperty-method"></a>IMetaDataEmit::DefineProperty (Método)
Crea una definición de propiedad para el `get` `set` tipo especificado, con los descriptores de acceso especificados y de método, y obtiene un token a esa definición de propiedad.  
  
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
 [en] El token para la clase o interfaz en la que se está definiendo la propiedad.  
  
 `szProperty`  
 [in] Nombre de la propiedad.  
  
 `dwPropFlags`  
 [en] Las marcas de propiedad.  
  
 `pvSig`  
 [en] La firma de la propiedad.  
  
 `cbSig`  
 [en] El recuento de `pvSig`bytes en .  
  
 `dwCPlusTypeFlag`  
 [en] El tipo del valor predeterminado de la propiedad.  
  
 `pValue`  
 [en] El valor predeterminado de la propiedad.  
  
 `cchValue`  
 [en] El recuento de caracteres `pValue`(Unicode) en .  
  
 `mdSetter`  
 [en] El método que establece el valor de propiedad.  
  
 `mdGetter`  
 [en] El método que obtiene el valor de propiedad.  
  
 `rmdOtherMethods[]`  
 [en] Matriz de otros métodos asociados a la propiedad. Termine la matriz `mdTokenNil`con un archivo .  
  
 `pmdProp`  
 [fuera] El `mdProperty` token asignado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
