---
title: IMetaDataImport::EnumTypeDefs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: 4545f5f8d78e588c655a72340210a785b0feb619
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720417"
---
# <a name="imetadataimportenumtypedefs-method"></a>IMetaDataImport::EnumTypeDefs (Método)

Enumera los tokens de TypeDef que representan todos los tipos en el ámbito actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `phEnum`  
 enuncia Puntero al nuevo enumerador. Debe ser NULL para la primera llamada de este método.  
  
 `rTypeDefs`  
 de Matriz que se usa para almacenar los tokens TypeDef.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rTypeDefs`.  
  
 `pcTypeDefs`  
 enuncia El número de tokens TypeDef devueltos en `rTypeDefs` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` se devolvió correctamente.|  
|`S_FALSE`|No hay tokens que enumerar. En ese caso, `pcTypeDefs` es cero.|  
  
## <a name="remarks"></a>Comentarios  

 El token TypeDef representa un tipo como una clase o una interfaz, así como cualquier tipo agregado a través de un mecanismo de extensibilidad.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
