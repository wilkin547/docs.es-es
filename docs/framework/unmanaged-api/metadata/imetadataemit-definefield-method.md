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
ms.openlocfilehash: 8ca5ab70f60de4d783800fb18612a8f04cb9cee1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177714"
---
# <a name="imetadataemitdefinefield-method"></a>IMetaDataEmit::DefineField (Método)
Crea una definición para un campo con la firma de metadatos especificada y obtiene un token a esa definición de campo.  
  
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
 [en] El `mdTypeDef` token para la clase o interfaz envolvente.  
  
 `szName`  
 [en] El nombre del campo en Unicode.  
  
 `dwFieldFlags`  
 [en] Los atributos de campo. Esta es una `CorFieldAttr` máscara de bits de valores.  
  
 `pvSigBlob`  
 [en] La firma de campo como BLOB.  
  
 `cbSigBlob`  
 [en] El recuento de `pvSigBlob`bytes en .  
  
 `dwCPlusTypeFlag`  
 [en] El `ELEMENT_TYPE_` *\** valor constante for. Este es `CorElementType` un valor. Si no define un valor constante `ELEMENT_TYPE_END`para el campo, utilice .  
  
 `pValue`  
 [en] El valor constante para el campo.  
  
 `cchValue`  
 [en] El tamaño en caracteres `pValue`(Unicode) de .  
  
 `pmd`  
 [fuera] El `mdFieldDef` token asignado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
