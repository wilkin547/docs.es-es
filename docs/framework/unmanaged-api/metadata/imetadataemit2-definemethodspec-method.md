---
title: IMetaDataEmit2::DefineMethodSpec (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce6df232f3793b8b61d9fa7c18c9c90ca9fa3900
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184722"
---
# <a name="imetadataemit2definemethodspec-method"></a>IMetaDataEmit2::DefineMethodSpec (Método)
Crea una instancia de un método genérica y obtiene un token a la definición.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `tkParent`  
 [in] Un token para el método que se va a crear la instancia genérica. El token debe ser de tipo `mdMethodDef` o `mdMemberRef`.  
  
 `pvSigBlob`  
 [in] Un puntero a la firma COM + binaria del método.  
  
 `cbSibBlob`  
 [in] El tamaño, en bytes, de `pvSigBlob`.  
  
 `pmi`  
 [out] Un token a la definición de la firma de metadatos del método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit2 (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataEmit (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
