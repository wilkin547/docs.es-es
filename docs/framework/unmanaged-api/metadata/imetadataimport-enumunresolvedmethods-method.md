---
title: IMetaDataImport::EnumUnresolvedMethods (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74d0c2e9777a7bd3d49622fb326ecb6b58fbec07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782543"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a>IMetaDataImport::EnumUnresolvedMethods (Método)
Enumera los tokens de MemberDef que representan los métodos no resueltos en el ámbito de metadatos actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `phEnum`  
 [in, out] Un puntero en el enumerador. Esto debe ser NULL para la primera llamada de este método.  
  
 `rMethods`  
 [out] Matriz utilizada para almacenar los tokens de MemberDef.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rMethods`.  
  
 `pcTokens`  
 [out] El número de tokens de MemberDef devueltos en `rMethods`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|DESCRIPCIÓN|  
|-------------|-----------------|  
|`S_OK`|`EnumUnresolvedMethods` se devolvió correctamente.|  
|`S_FALSE`|No hay ningún token para enumerar. En ese caso, `pcTokens` es cero.|  
  
## <a name="remarks"></a>Comentarios  
 Un método sin resolver es aquella que se ha declarado pero no implementado. Un método se incluye en la enumeración si el método se marca `miForwardRef` y `mdPinvokeImpl` o `miRuntime` se establece en cero. En otras palabras, un método sin resolver es un método de clase marcado `miForwardRef` pero que no se implementa en código no administrado (llegado a través de PInvoke) ni implementada internamente por el tiempo de ejecución  
  
 La enumeración excluye todos los métodos que se definen en el ámbito de módulo (globales) o en interfaces o clases abstractas.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
