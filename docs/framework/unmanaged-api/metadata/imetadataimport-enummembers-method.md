---
title: IMetaDataImport::EnumMembers (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
ms.openlocfilehash: 92503df60ae44dfd44819fe3eda8e6a0549b2b66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721000"
---
# <a name="imetadataimportenummembers-method"></a>IMetaDataImport::EnumMembers (Método)

Enumera los tokens de MemberDef que representan a miembros del tipo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `phEnum`  
 [in, out] Puntero al enumerador.  
  
 `cl`  
 de Un token de TypeDef que representa el tipo cuyos miembros se van a enumerar.  
  
 `rMembers`  
 enuncia Matriz usada para contener los tokens de MemberDef.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rMembers`.  
  
 `pcTokens`  
 enuncia Número real de tokens de MemberDef devueltos en `rMembers` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers` se devolvió correctamente.|  
|`S_FALSE`|No hay tokens de MemberDef que enumerar. En ese caso, `pcTokens` es cero.|  
  
## <a name="remarks"></a>Comentarios  

 Al enumerar colecciones de miembros para una clase, `EnumMembers` solo devuelve los miembros (campos y métodos, pero **no** propiedades o eventos) definidos directamente en la clase. No devuelve ningún miembro que la clase herede, aunque la clase proporcione una implementación para esos miembros heredados. Para enumerar los miembros heredados, el llamador debe recorrer explícitamente la cadena de herencia. Tenga en cuenta que las reglas para la cadena de herencia pueden variar en función del lenguaje o del compilador que emitió los metadatos originales.

 No enumera las propiedades y los eventos `EnumMembers` . Para enumerarlos, use [EnumProperties (](imetadataimport-enumproperties-method.md) o [enumevents (](imetadataimport-enumevents-method.md).
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
