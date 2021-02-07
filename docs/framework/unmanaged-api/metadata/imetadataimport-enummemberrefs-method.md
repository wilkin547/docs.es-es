---
description: 'Más información sobre: IMetaDataImport:: EnumMemberRefs ((método)'
title: IMetaDataImport::EnumMemberRefs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
ms.openlocfilehash: 0c9b10342f73ae5b604ac25b6ff8ccec58deb5ab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670949"
---
# <a name="imetadataimportenummemberrefs-method"></a>IMetaDataImport::EnumMemberRefs (Método)

Enumera los tokens de MemberRef que representan a miembros del tipo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `phEnum`  
 [in, out] Puntero al enumerador.  
  
 `tkParent`  
 de Un token TypeDef, TypeRef, MethodDef o ModuleRef para el tipo cuyos miembros se van a enumerar.  
  
 `rMemberRefs`  
 enuncia Matriz utilizada para almacenar los tokens de MemberRef.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rMemberRefs`.  
  
 `pcTokens`  
 enuncia Número real de tokens de MemberRef devueltos en `rMemberRefs` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumMemberRefs` se devolvió correctamente.|  
|`S_FALSE`|No hay tokens de MemberRef que enumerar. En ese caso, `pcTokens` es a cero.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
