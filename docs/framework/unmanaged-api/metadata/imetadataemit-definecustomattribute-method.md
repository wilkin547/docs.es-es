---
title: IMetaDataEmit::DefineCustomAttribute (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a11e9919dc1338c4b67c3c4b0f082e330c29d9eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitdefinecustomattribute-method"></a>IMetaDataEmit::DefineCustomAttribute (Método)
Crea una definición para un atributo personalizado con la firma de metadatos especificados, que se adjuntará al objeto especificado y obtiene un símbolo (token) para esa definición de atributo personalizado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `tkObj`  
 [in] El token para el elemento de propietario.  
  
 `tkType`  
 [in] El token que identifica el atributo personalizado.  
  
 `pCustomAttribute`  
 [in] Un puntero al atributo personalizado.  
  
 `cbCustomAttribute`  
 [in] El recuento de bytes en `pCustomAttribute`.  
  
 `pcv`  
 [out] El `mdCustomAttribute` token asignado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
