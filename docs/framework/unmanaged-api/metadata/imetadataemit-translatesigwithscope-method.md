---
description: 'Más información sobre: IMetaDataEmit:: TranslateSigWithScope ((método)'
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
ms.openlocfilehash: e5f4e522e993f2f391ca0c29e5fcc2cbb71775e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720939"
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
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyEmit (Interfaz)](imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport (Interfaz)](imetadataassemblyimport-interface.md)
- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
