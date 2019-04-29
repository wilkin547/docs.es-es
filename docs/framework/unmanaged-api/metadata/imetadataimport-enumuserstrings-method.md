---
title: IMetaDataImport::EnumUserStrings (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUserStrings
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4be12e46851b11a5e6db60c351094a356fa61f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777934"
---
# <a name="imetadataimportenumuserstrings-method"></a>IMetaDataImport::EnumUserStrings (Método)
Enumera los tokens de String que representan las cadenas codificadas de forma rígida en el ámbito de metadatos actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `phEnum`  
 [in, out] Un puntero en el enumerador. Esto debe ser NULL para la primera llamada de este método.  
  
 `rStrings`  
 [out] Matriz utilizada para almacenar los tokens de cadena.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rStrings`.  
  
 `pcStrings`  
 [out] El número de tokens de cadena devueltos en `rStrings`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumUserStrings` se devolvió correctamente.|  
|`S_FALSE`|No hay ningún token para enumerar. En ese caso, `pcStrings` es cero.|  
  
## <a name="remarks"></a>Comentarios  
 Los tokens de cadena se crean mediante el [DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) método. Este método está diseñado para usarse mediante un explorador de metadatos en lugar de un compilador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
