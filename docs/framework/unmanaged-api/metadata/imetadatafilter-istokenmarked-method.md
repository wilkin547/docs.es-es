---
title: IMetaDataFilter::IsTokenMarked (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.IsTokenMarked
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 32642c4ff6193e2002c8a4c7d201b36c7601debb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582544"
---
# <a name="imetadatafilteristokenmarked-method"></a>IMetaDataFilter::IsTokenMarked (Método)
Obtiene un valor que indica si el token de metadatos especificado se ha marcado como procesado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `tk`  
 [in] El token para examinar una marca de procesamiento.  
  
 `pIsMarked`  
 [out] Un valor que es `true` si `tk` se ha procesado; en caso contrario `false`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataFilter (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
