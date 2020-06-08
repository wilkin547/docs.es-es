---
title: IMetaDataImport::EnumPermissionSets (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
ms.openlocfilehash: 79b1493d262288c1d85a56538810e35a73441595
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491776"
---
# <a name="imetadataimportenumpermissionsets-method"></a>IMetaDataImport::EnumPermissionSets (Método)
Enumera los permisos de los objetos en un ámbito de metadatos especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `phEnum`  
 [in, out] Puntero al enumerador. Debe ser NULL para la primera llamada de este método.  
  
 `tk`  
 de Un token de metadatos que limita el ámbito de la búsqueda o NULL para buscar el ámbito más amplio posible.  
  
 `dwActions`  
 de Marcas que representan los <xref:System.Security.Permissions.SecurityAction> valores que se van a incluir en `rPermission` , o cero, para devolver todas las acciones.  
  
 `rPermission`  
 enuncia Matriz utilizada para almacenar los tokens de permiso.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rPermission`.  
  
 `pcTokens`  
 enuncia El número de tokens de permiso devueltos en `rPermission` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumPermissionSets`se devolvió correctamente.|  
|`S_FALSE`|No hay tokens que enumerar. En ese caso, `pcTokens` es cero.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
