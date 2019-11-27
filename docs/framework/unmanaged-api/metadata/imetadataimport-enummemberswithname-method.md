---
title: IMetaDataImport::EnumMembersWithName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
ms.openlocfilehash: ed193aab8beb0de1321aa1d52ec9f963b08b316c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441665"
---
# <a name="imetadataimportenummemberswithname-method"></a>IMetaDataImport::EnumMembersWithName (Método)
Enumera los tokens de MemberDef que representan a miembros del tipo especificado con el nombre especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [in]      LPCWSTR     szName,   
   [out]     mdToken     rMembers[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `phEnum`  
 [in, out] Puntero al enumerador.  
  
 `cl`  
 de Un token de TypeDef que representa el tipo con miembros que se van a enumerar.  
  
 `szName`  
 de Nombre del miembro que limita el ámbito del enumerador.  
  
 `rMembers`  
 enuncia Matriz utilizada para almacenar los tokens de MemberDef.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rMembers`.  
  
 `pcTokens`  
 enuncia Número real de tokens de MemberDef devueltos en `rMembers`.  
  
## <a name="remarks"></a>Comentarios  
 Este método enumera los campos y métodos, pero no las propiedades o los eventos. A diferencia de [IMetaDataImport:: EnumMembers (](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` descarta todos los tokens de campo y miembro que no tienen el nombre especificado.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` devolvió correctamente.|  
|`S_FALSE`|No hay tokens de MemberDef que enumerar. En ese caso, `pcTokens` es cero.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
