---
title: IMetaDataTables::GetCodedTokenInfo (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
ms.openlocfilehash: 8ab16ad5b2b2838125e07511ef47be737f40671c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501214"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a>IMetaDataTables::GetCodedTokenInfo (Método)
Obtiene un puntero a una matriz de tokens asociada al índice de fila especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ixCdTkn`  
 de El tipo de token codificado que se va a devolver.  
  
 `pcTokens`  
 enuncia Puntero a la longitud de `ppTokens` .  
  
 `ppTokens`  
 enuncia Un puntero a un puntero a una matriz que contiene la lista de tokens devueltos.  
  
 `ppName`  
 enuncia Un puntero a un puntero al nombre del token en `ixCdTkn` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [IMetaDataTables (Interfaz)](imetadatatables-interface.md)
- [IMetaDataTables2 (Interfaz)](imetadatatables2-interface.md)
