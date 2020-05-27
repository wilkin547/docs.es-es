---
title: IMetaDataEmit::DefineField (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: ccc4843864f375c167acdb12575c282dbe3a49e1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004821"
---
# <a name="imetadataemitdefinefield-method"></a>IMetaDataEmit::DefineField (Método)
Crea una definición para un campo con la firma de metadatos especificada y obtiene un token para esa definición de campo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineField (
    [in]  mdTypeDef   td,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwFieldFlags,
    [in]  PCCOR_SIGNATURE pvSigBlob,
    [in]  ULONG       cbSigBlob,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue,
    [out] mdFieldDef  *pmd
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `td`  
 de `mdTypeDef`Token de la clase o interfaz envolvente.  
  
 `szName`  
 de Nombre del campo en Unicode.  
  
 `dwFieldFlags`  
 de Atributos del campo. Se trata de una máscara de máscara de `CorFieldAttr` valores.  
  
 `pvSigBlob`  
 de La firma del campo como un BLOB.  
  
 `cbSigBlob`  
 de Recuento de bytes de `pvSigBlob` .  
  
 `dwCPlusTypeFlag`  
 de `ELEMENT_TYPE_` *\** Para el valor constante. Este es un `CorElementType` valor. Si no se define un valor constante para el campo, use `ELEMENT_TYPE_END` .  
  
 `pValue`  
 de Valor constante para el campo.  
  
 `cchValue`  
 de El tamaño en caracteres (Unicode) de `pValue` .  
  
 `pmd`  
 enuncia El `mdFieldDef` token asignado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
