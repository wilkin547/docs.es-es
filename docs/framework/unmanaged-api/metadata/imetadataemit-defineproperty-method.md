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
ms.openlocfilehash: d2a4a15126f34666a58021a59e9e193685b15a49
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719494"
---
# <a name="imetadataemitdefineproperty-method"></a>IMetaDataEmit::DefineProperty (Método)

Crea una definición de propiedad para el tipo especificado, con los `get` descriptores de acceso de los métodos y especificados `set` , y obtiene un token para esa definición de propiedad.  
  
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
 [in] Nombre de la propiedad.  
  
 `dwPropFlags`  
 de Marcas de propiedad.  
  
 `pvSig`  
 de Firma de la propiedad.  
  
 `cbSig`  
 de Recuento de bytes de `pvSig` .  
  
 `dwCPlusTypeFlag`  
 de Tipo del valor predeterminado de la propiedad.  
  
 `pValue`  
 de Valor predeterminado de la propiedad.  
  
 `cchValue`  
 de Recuento de caracteres (Unicode) en `pValue` .  
  
 `mdSetter`  
 de El método que establece el valor de propiedad.  
  
 `mdGetter`  
 de Método que obtiene el valor de propiedad.  
  
 `rmdOtherMethods[]`  
 de Matriz de otros métodos asociados a la propiedad. Finalice la matriz con un `mdTokenNil` .  
  
 `pmdProp`  
 enuncia El `mdProperty` token asignado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
