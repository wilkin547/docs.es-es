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
ms.openlocfilehash: 80d33da2eb2a7f0cfbe5dcb7279fff9973dada2e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712929"
---
# <a name="imetadataemittranslatesigwithscope-method"></a>IMetaDataEmit::TranslateSigWithScope (Método)

Importa un ensamblado en el ámbito actual y obtiene una nueva firma de metadatos para el ámbito combinado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de Interfaz para el ensamblado de importación (donde se define la firma).  
  
 `pbHashValue`  
 de Objeto binario hash para el ensamblado.  
  
 `cbHashValue`  
 de Recuento de bytes de `pbHashValue` .  
  
 `import`  
 de La interfaz para importar el ámbito de metadatos.  
  
 `pbSigBlob`  
 de Firma que se va a importar.  
  
 `cbSigBlob`  
 de Tamaño, en bytes, de `pbSigBlob` .  
  
 `pAssemEmit`  
 de Interfaz para el ensamblado de exportación.  
  
 `emit`  
 de La interfaz para el ámbito de exportación de metadatos.  
  
 `pvTranslatedSig`  
 enuncia Búfer que va a contener el BLOB de firma traducido.  
  
 `cbTranslatedSigMax`  
 de Capacidad, en bytes, de `pvTranslatedSig` .  
  
 `pcbTranslatedSig`  
 enuncia Número de bytes reales de la firma traducida.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataAssemblyEmit (Interfaz)](imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport (Interfaz)](imetadataassemblyimport-interface.md)
- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
