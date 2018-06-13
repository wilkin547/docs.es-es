---
title: IMetaDataImport::EnumEvents (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumEvents
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 608b4a7d147124ede60e9d81f91600dfdaad0a65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446501"
---
# <a name="imetadataimportenumevents-method"></a>IMetaDataImport::EnumEvents (Método)
Enumera los tokens de definición de eventos del token de TypeDef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `phEnum`  
 [entrada, salida] Un puntero para el enumerador.  
  
 `td`  
 [in] El token de TypeDef cuyas definiciones de evento que se van a enumerar.  
  
 `rEvents`  
 [out] Matriz de eventos devueltos.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rEvents`.  
  
 `pcEvents`  
 [out] El número real de eventos devueltos en `rEvents`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumEvents` se devolvió correctamente.|  
|`S_FALSE`|No hay ningún evento para enumerar. En ese caso, `pcEvents` es cero.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
