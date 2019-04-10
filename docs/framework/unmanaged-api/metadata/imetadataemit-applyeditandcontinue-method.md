---
title: IMetaDataEmit::ApplyEditAndContinue (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.ApplyEditAndContinue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::ApplyEditAndContinue
helpviewer_keywords:
- ApplyEditAndContinue method [.NET Framework metadata]
- IMetaDataEmit::ApplyEditAndContinue method [.NET Framework metadata]
ms.assetid: 35991289-f389-495d-8caa-a6384fb1d557
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c18c72ecbaf2e0d3153ad7f00caf73421e35fa0a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225318"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a>IMetaDataEmit::ApplyEditAndContinue (Método)
El ámbito de ensamblado actual se actualiza con los cambios realizados en los metadatos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pImport`  
 \[en\] puntero a un [IUnknown](/cpp/atl/iunknown) objeto que representa los metadatos delta del archivo portable ejecutable (PE).
  
 Los metadatos delta están el bloque de metadatos que incluyen los cambios realizados en la copia de los metadatos del módulo real.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
