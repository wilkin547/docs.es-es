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
ms.openlocfilehash: 2807458549db02598ba05f2aa80fa6ea6fbc5a13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177693"
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
 [en] El token para el método cuyo parámetro se está definiendo.  
  
 `ulParamSeq`  
 [en] El número de secuencia de parámetros.  
  
 `szName`  
 [en] El nombre del parámetro en Unicode.  
  
 `dwParamFlags`  
 [en] Indicadores para el parámetro. Esta es una `CorParamAttr` máscara de bits de valores.  
  
 `dwCPlusTypeFlag`  
 [en] `ELEMENT_TYPE_` para el valor *\** constante.  
  
 `pValue`  
 [en] El valor constante del parámetro.  
  
 `cchValue`  
 [en] El tamaño, en caracteres Unicode, de `pValue`.  
  
 `ppd`  
 [fuera] El `mdParamDef` token asignado.  
  
## <a name="remarks"></a>Observaciones  
 Los valores `ulParamSeq` de secuencia comienzan con 1 para los parámetros. Un valor devuelto tiene un número de secuencia de 0.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
