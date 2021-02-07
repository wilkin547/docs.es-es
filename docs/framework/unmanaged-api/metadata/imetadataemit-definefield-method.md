---
description: 'Más información acerca de: IMetaDataEmit::D método efineField'
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
ms.openlocfilehash: 7636b1521de721cc183305e8a0763ff0a61f331b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753451"
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
 de `mdTypeDef` Token de la clase o interfaz envolvente.  
  
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
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
