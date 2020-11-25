---
title: IMetaDataEmit::DefineParam (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
ms.openlocfilehash: 5b3f89bb14be0d7128682f8702548545b1e50928
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719533"
---
# <a name="imetadataemitdefineparam-method"></a>IMetaDataEmit::DefineParam (Método)

Crea una definición de parámetro con la firma especificada para el método al que hace referencia el token especificado y obtiene un token para esa definición de parámetro.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineParam (  
    [in]  mdMethodDef md,
    [in]  ULONG       ulParamSeq,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,
    [out] mdParamDef  *ppd
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `md`  
 de El token para el método cuyo parámetro se está definiendo.  
  
 `ulParamSeq`  
 de El número de secuencia del parámetro.  
  
 `szName`  
 de Nombre del parámetro en Unicode.  
  
 `dwParamFlags`  
 de Marcas para el parámetro. Se trata de una máscara de máscara de `CorParamAttr` valores.  
  
 `dwCPlusTypeFlag`  
 [in] `ELEMENT_TYPE_` *\** para el valor constante.  
  
 `pValue`  
 de Valor constante para el parámetro.  
  
 `cchValue`  
 de Tamaño, en caracteres Unicode, de `pValue` .  
  
 `ppd`  
 enuncia El `mdParamDef` token asignado.  
  
## <a name="remarks"></a>Comentarios  

 Los valores de secuencia de `ulParamSeq` comienzan por 1 para los parámetros. Un valor devuelto tiene un número de secuencia de 0.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
