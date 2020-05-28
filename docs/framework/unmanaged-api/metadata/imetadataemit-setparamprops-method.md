---
title: IMetaDataEmit::SetParamProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: b710f966f519e2702607b7e186fff5986110d391
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007824"
---
# <a name="imetadataemitsetparamprops-method"></a>IMetaDataEmit::SetParamProps (Método)
Establece o cambia las características de un parámetro de método que se definió mediante una llamada anterior a [IMetaDataEmit::D efineparam](imetadataemit-defineparam-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetParamProps (
    [in]  mdParamDef  pd,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pd`  
 de El token para el parámetro de destino.  
  
 `szName`  
 de Nombre del parámetro en Unicode.  
  
 `dwParamFlags`  
 de Marcas para el parámetro.  
  
 `dwCPlusTypeFlag`  
 de ELEMENT_TYPE_ * para el valor constante.  
  
 `pValue`  
 de Valor constante para el parámetro.  
  
 `cchValue`  
 de El tamaño en caracteres (Unicode) de `pValue` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
