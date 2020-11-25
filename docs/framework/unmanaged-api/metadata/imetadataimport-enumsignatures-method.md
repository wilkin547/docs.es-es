---
title: IMetaDataImport::EnumSignatures (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
ms.openlocfilehash: 3021124184ab0491337a07144e6f77b5bfea3681
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721977"
---
# <a name="imetadataimportenumsignatures-method"></a>IMetaDataImport::EnumSignatures (Método)

Enumera los tokens de firma que representan las firmas independientes en el ámbito actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `phEnum`  
 [in, out] Puntero al enumerador. Debe ser NULL para la primera llamada de este método.  
  
 `rSignatures`  
 enuncia Matriz utilizada para almacenar los tokens de firma.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rSignatures`.  
  
 `pcSignatures`  
 enuncia El número de tokens de firma devueltos en `rSignatures` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumSignatures` se devolvió correctamente.|  
|`S_FALSE`|No hay tokens que enumerar. En ese caso, `pcSignatures` es cero.|  
  
## <a name="remarks"></a>Comentarios  

 El método [IMetaDataEmit:: GetTokenFromSig (](imetadataemit-gettokenfromsig-method.md) crea los tokens de firma.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
