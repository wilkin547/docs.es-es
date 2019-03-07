---
title: IMetaDataEmit::TranslateSigWithScope (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1243a5ed1a3b741f1691cc4f0847ddcf17ac9669
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478393"
---
# <a name="imetadataemittranslatesigwithscope-method"></a>IMetaDataEmit::TranslateSigWithScope (Método)
Importa un ensamblado en el ámbito actual y obtiene una nueva firma de metadatos para el ámbito combinado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT TranslateSigWithScope (   
    [in]  IMetaDataAssemblyImport   *pAssemImport,   
    [in]  const void                *pbHashValue,   
    [in]  ULONG                     cbHashValue,   
    [in]  IMetaDataImport           *import,   
    [in]  PCCOR_SIGNATURE           pbSigBlob,   
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,   
    [in]  IMetaDataEmit             *emit,   
    [out] PCOR_SIGNATURE            pvTranslatedSig,   
    [in]  ULONG                     cbTranslatedSigMax,   
    [out] ULONG                     *pcbTranslatedSig   
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pAssemImport`  
 [in] La interfaz de ensamblado de importación (donde se define la firma).  
  
 `pbHashValue`  
 [in] El blob de hash para el ensamblado.  
  
 `cbHashValue`  
 [in] El recuento de bytes en `pbHashValue`.  
  
 `import`  
 [in] La interfaz para el ámbito de metadatos de importación.  
  
 `pbSigBlob`  
 [in] La firma que desea importar.  
  
 `cbSigBlob`  
 [in] El tamaño, en bytes, de `pbSigBlob`.  
  
 `pAssemEmit`  
 [in] La interfaz de ensamblado de exportación.  
  
 `emit`  
 [in] La interfaz para el ámbito de metadatos de exportación.  
  
 `pvTranslatedSig`  
 [out] El búfer para almacenar el objeto binario de firma traducidos.  
  
 `cbTranslatedSigMax`  
 [in] La capacidad, en bytes, de `pvTranslatedSig`.  
  
 `pcbTranslatedSig`  
 [out] El número de bytes reales en la firma convertida.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
