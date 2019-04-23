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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e8d871f2ecbd96d5bda781b2ae11b94efd409442
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128406"
---
# <a name="imetadataimportenummembers-method"></a>IMetaDataImport::EnumMembers (Método)
Enumera los tokens de MemberDef que representan a miembros del tipo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
 [in, out] Un puntero en el enumerador.  
  
 `cl`  
 [in] Un token de TypeDef que representa el tipo cuyos miembros se van a enumerar.  
  
 `rMembers`  
 [out] Matriz utilizada para almacenar los tokens de MemberDef.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rMembers`.  
  
 `pcTokens`  
 [out] El número real de los tokens de MemberDef devueltos en `rMembers`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers` se devolvió correctamente.|  
|`S_FALSE`|No hay ningún token MemberDef para enumerar. En ese caso, `pcTokens` es cero.|  
  
## <a name="remarks"></a>Comentarios  
 Al enumerar las colecciones de miembros para una clase, `EnumMembers` devuelve solo los miembros (campos y métodos, pero **no** propiedades o eventos) definidos directamente en la clase. No devuelve a los miembros que hereda de la clase, incluso si la clase proporciona una implementación para esos miembros heredados. Para enumerar los miembros heredados, el llamador debe recorrer explícitamente la cadena de herencia. Tenga en cuenta que las reglas para la cadena de herencia pueden variar dependiendo del lenguaje o del compilador que genera los metadatos originales.
 
 No se enumeran las propiedades y eventos mediante `EnumMembers`. Para enumerarlos, utilice [EnumProperties](imetadataimport-enumproperties-method.md) o [EnumEvents](imetadataimport-enumevents-method.md).
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
