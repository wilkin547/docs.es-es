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
ms.openlocfilehash: 40f24a4ea628ce92a27ab1bfe97fc87a57dfa4f0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432546"
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
 de El token de `mdTypeDef` de la clase o interfaz envolvente.  
  
 `szName`  
 de Nombre del campo en Unicode.  
  
 `dwFieldFlags`  
 de Atributos del campo. Se trata de una máscara de máscara de valores `CorFieldAttr`.  
  
 `pvSigBlob`  
 de La firma del campo como un BLOB.  
  
 `cbSigBlob`  
 de Recuento de bytes de `pvSigBlob`.  
  
 `dwCPlusTypeFlag`  
 de *\** de `ELEMENT_TYPE_`para el valor constante. Se trata de un valor de `CorElementType`. Si no se define un valor constante para el campo, utilice `ELEMENT_TYPE_END`.  
  
 `pValue`  
 de Valor constante para el campo.  
  
 `cchValue`  
 de El tamaño en caracteres (Unicode) de `pValue`.  
  
 `pmd`  
 enuncia El token de `mdFieldDef` asignado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
