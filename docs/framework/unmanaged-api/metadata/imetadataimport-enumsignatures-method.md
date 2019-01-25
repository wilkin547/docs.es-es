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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 61285b3de76f556b498c9815508275989eb96807
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630988"
---
# <a name="imetadataimportenumsignatures-method"></a>IMetaDataImport::EnumSignatures (Método)
Enumera los tokens de firma que representan las firmas independientes en el ámbito actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `phEnum`  
 [in, out] Un puntero en el enumerador. Esto debe ser NULL para la primera llamada de este método.  
  
 `rSignatures`  
 [out] Matriz utilizada para almacenar los tokens de firma.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rSignatures`.  
  
 `pcSignatures`  
 [out] El número de tokens de firma que se devuelven en `rSignatures`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumSignatures` se devolvió correctamente.|  
|`S_FALSE`|No hay ningún token para enumerar. En ese caso, `pcSignatures` es cero.|  
  
## <a name="remarks"></a>Comentarios  
 Los tokens de firma se crean mediante el [GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
