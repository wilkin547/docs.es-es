---
description: 'Más información sobre: IMetaDataImport:: EnumFieldsWithName ((método)'
title: IMetaDataImport::EnumFieldsWithName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFieldsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type:
- apiref
ms.openlocfilehash: 88096b2b12a9571eb05d4550e6e26a348e28cfd2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799375"
---
# <a name="imetadataimportenumfieldswithname-method"></a>IMetaDataImport::EnumFieldsWithName (Método)

Enumera los tokens de FieldDef del tipo especificado con el nombre especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]  mdTypeDef       cl,
   [in]  LPCWSTR         szName,
   [out] mdFieldDef      rFields[],
   [in]  ULONG           cMax,
   [out] ULONG           *pcTokens
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `phEnum`  
 [in, out] Puntero al enumerador.  
  
 `cl`  
 de Token del tipo cuyos campos se van a enumerar.  
  
 `szName`  
 de Nombre del campo que limita el ámbito de la enumeración.  
  
 `rFields`  
 enuncia Matriz que se usa para almacenar los tokens de FieldDef.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rFields`.  
  
 `pcTokens`  
 enuncia Número real de tokens de FieldDef devueltos en `rFields` .  
  
## <a name="remarks"></a>Observaciones  

 A diferencia de [IMetaDataImport:: EnumFields](imetadataimport-enumfields-method.md), `EnumFieldsWithName` descarta todos los tokens de campo que no tienen el nombre especificado.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumFieldsWithName` se devolvió correctamente.|  
|`S_FALSE`|No hay campos que enumerar. En ese caso, `pcTokens` es cero.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
