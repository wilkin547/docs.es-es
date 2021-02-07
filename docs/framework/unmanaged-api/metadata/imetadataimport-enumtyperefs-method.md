---
description: 'Más información sobre: IMetaDataImport:: Enumtyperefs ((método)'
title: IMetaDataImport::EnumTypeRefs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type:
- apiref
ms.openlocfilehash: 1155357e82c08660a852225f0b1a54629cbee0ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670637"
---
# <a name="imetadataimportenumtyperefs-method"></a>IMetaDataImport::EnumTypeRefs (Método)

Enumera los tokens de TypeRef definidos en el ámbito de metadatos actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `phEnum`  
 [in, out] Puntero al enumerador. Debe ser NULL para la primera llamada de este método.  
  
 `rTypeRefs`  
 enuncia Matriz que se usa para almacenar los tokens de TypeRef.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rTypeRefs`.  
  
 `pcTypeRefs`  
 enuncia Puntero al número de tokens de TypeRef devueltos en `rTypeRefs` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeRefs` se devolvió correctamente.|  
|`S_FALSE`|No hay tokens que enumerar. En ese caso, `pcTypeRefs` es cero.|  
  
## <a name="remarks"></a>Observaciones  

 Un token TypeRef representa una referencia a un tipo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
