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
ms.openlocfilehash: ff9827174e43fd62f3a995e9f477c6fff66b227a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449957"
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
 [in, out] Puntero al enumerador. Debe ser NULL para la primera llamada de este método.  
  
 `rMethods`  
 enuncia Matriz utilizada para almacenar los tokens de MemberDef.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rMethods`.  
  
 `pcTokens`  
 enuncia El número de tokens de MemberDef devueltos en `rMethods`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumUnresolvedMethods` devolvió correctamente.|  
|`S_FALSE`|No hay tokens que enumerar. En ese caso, `pcTokens` es cero.|  
  
## <a name="remarks"></a>Comentarios  
 Un método sin resolver es aquel que se ha declarado pero no se ha implementado. Un método se incluye en la enumeración si el método está marcado `miForwardRef` y `mdPinvokeImpl` o `miRuntime` está establecido en cero. En otras palabras, un método sin resolver es un método de clase que está marcado como `miForwardRef` pero que no se implementa en código no administrado (se alcanza a través de PInvoke) ni lo implementa internamente el propio Runtime.  
  
 La enumeración excluye todos los métodos que se definen en el ámbito del módulo (Globals) o en interfaces o clases abstractas.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
