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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c2509945d2799b81e036888d146a51cee87fda09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169850"
---
# <a name="imetadataimportenummemberswithname-method"></a>IMetaDataImport::EnumMembersWithName (Método)
Enumera los tokens de MemberDef que representan a miembros del tipo especificado con el nombre especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
 [in, out] Un puntero en el enumerador.  
  
 `cl`  
 [in] Un token de TypeDef que representa el tipo con miembros para enumerar.  
  
 `szName`  
 [in] El nombre de miembro que limita el ámbito del enumerador.  
  
 `rMembers`  
 [out] Matriz utilizada para almacenar los tokens de MemberDef.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rMembers`.  
  
 `pcTokens`  
 [out] El número real de los tokens de MemberDef devueltos en `rMembers`.  
  
## <a name="remarks"></a>Comentarios  
 Este método enumera los campos y métodos, pero no las propiedades o eventos. A diferencia de [EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` descarta todos los tokens de campo y los miembros que no tienen el nombre especificado.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` se devolvió correctamente.|  
|`S_FALSE`|No hay ningún token MemberDef para enumerar. En ese caso, `pcTokens` es cero.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
