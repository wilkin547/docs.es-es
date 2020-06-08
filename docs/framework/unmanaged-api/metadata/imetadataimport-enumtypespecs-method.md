---
title: IMetaDataImport::EnumTypeSpecs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
ms.openlocfilehash: 94b4c3935c949c0c4008e41244713b6bfa4dba84
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503723"
---
# <a name="imetadataimportenumtypespecs-method"></a>IMetaDataImport::EnumTypeSpecs (Método)
Enumera los tokens de TypeSpec definidos en el ámbito de metadatos actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `phEnum`  
 [in, out] Puntero al enumerador. Este valor debe ser NULL para la primera llamada de este método.  
  
 `rTypeSpecs`  
 enuncia Matriz usada para almacenar los tokens de TypeSpec.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rTypeSpecs`.  
  
 `pcTypeSpecs`  
 enuncia Número de tokens de TypeSpec devueltos en `rTypeSpecs` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeSpecs`se devolvió correctamente.|  
|`S_FALSE`|No hay tokens que enumerar. En ese caso, `pcTypeSpecs` es cero.|  
  
## <a name="remarks"></a>Comentarios  
 El método [IMetaDataEmit:: GetTokenFromTypeSpec (](imetadataemit-gettokenfromtypespec-method.md) crea los tokens TypeSpec.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
