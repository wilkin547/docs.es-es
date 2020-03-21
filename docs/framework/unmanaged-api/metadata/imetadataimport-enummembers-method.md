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
ms.openlocfilehash: 20c7a90f27defa18a5ef311d1f3a549b81fc5c40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175491"
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
 [adentro, fuera] Un puntero al enumerador.  
  
 `cl`  
 [en] Un token TypeDef que representa el tipo cuyos miembros se van a enumerar.  
  
 `rMembers`  
 [fuera] Matriz utilizada para contener los tokens MemberDef.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rMembers`.  
  
 `pcTokens`  
 [fuera] El número real de tokens `rMembers`MemberDef devueltos en .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers`regresó con éxito.|  
|`S_FALSE`|No hay tokens MemberDef que enumerar. En ese `pcTokens` caso, es cero.|  
  
## <a name="remarks"></a>Observaciones  
 Al enumerar colecciones de miembros para una clase, `EnumMembers` devuelve solo los miembros (campos y métodos, pero **no** las propiedades o eventos) definidos directamente en la clase. No devuelve ningún miembro que herede la clase, incluso si la clase proporciona una implementación para esos miembros heredados. Para enumerar los miembros heredados, el llamador debe recorrer explícitamente la cadena de herencia. Tenga en cuenta que las reglas de la cadena de herencia pueden variar en función del lenguaje o compilador que emitió los metadatos originales.

 Las propiedades y los `EnumMembers`eventos no se enumeran mediante . Para enumerarlos, utilice [EnumProperties](imetadataimport-enumproperties-method.md) o [EnumEvents](imetadataimport-enumevents-method.md).
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
