---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 024ab8254f566e5386198fa1735af4c6b1972ca1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448041"
---
# <a name="imetadataemitsetpropertyprops-method"></a>IMetaDataEmit::SetPropertyProps (Método)
Establece las características que se almacenan en los metadatos para una propiedad definida por una llamada anterior a [método DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
#### <a name="parameters"></a>Parámetros  
 `pr`  
 [in] El token para la propiedad que se va a cambiar  
  
 `dwPropFlags`  
 [in] Marcas de propiedad.  
  
 `dwCPlusTypeFlag`  
 [in] El tipo de valor predeterminado de la propiedad.  
  
 `pValue`  
 [in] El valor predeterminado para la propiedad.  
  
 `cchValue`  
 [in] El recuento de (Unicode) caracteres de `pValue`.  
  
 `mdSetter`  
 [in] El método que establece el valor de propiedad.  
  
 `mdGetter`  
 [in] El método que obtiene el valor de propiedad.  
  
 `rmdOtherMethods[]`  
 [in] Una matriz de otros métodos asociados a la propiedad. Finalizar esta matriz con un `mdTokenNil` símbolo (token).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
