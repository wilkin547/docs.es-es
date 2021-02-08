---
description: 'Más información sobre: IMetaDataEmit:: Setpropertyprops ((método)'
title: IMetaDataEmit::SetPropertyProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
ms.openlocfilehash: ad5efa86b4f774bcaa2251cb992c2dd52ac28bdd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771839"
---
# <a name="imetadataemitsetpropertyprops-method"></a>IMetaDataEmit::SetPropertyProps (Método)

Establece las características almacenadas en los metadatos de una propiedad definida por una llamada anterior al [método DefineProperty](imetadataemit-defineproperty-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetPropertyProps (
    [in]  mdProperty      pr,
    [in]  DWORD           dwPropFlags,
    [in]  DWORD           dwCPlusTypeFlag,
    [in]  void const      *pValue,
    [in]  ULONG           cchValue,
    [in]  mdMethodDef     mdSetter,
    [in]  mdMethodDef     mdGetter,
    [in]  mdMethodDef     rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pr`  
 de Token para la propiedad que se va a cambiar.  
  
 `dwPropFlags`  
 de Marcas de propiedad.  
  
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
 de Matriz de otros métodos asociados a la propiedad. Termine esta matriz con un `mdTokenNil` token.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
