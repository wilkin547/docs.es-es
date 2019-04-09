---
title: IMetaDataEmit::DefinePermissionSet (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33eadccf691b14289a46ff460f3cef8ae636b129
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074851"
---
# <a name="imetadataemitdefinepermissionset-method"></a>IMetaDataEmit::DefinePermissionSet (Método)
Crea una definición para un conjunto de permisos con la firma de metadatos especificado y obtiene un token para esa definición del conjunto de permisos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `tk`  
 [in] El objeto que va a ser representativo.  
  
 `dwAction`  
 [in] Un [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) valor que especifica el tipo de seguridad declarativa para usarse.  
  
 `pvPermission`  
 [in] El permiso de BLOB.  
  
 `cbPermission`  
 [in] El tamaño, en bytes, de `pvPermission`.  
  
 `ppm`  
 [out] El token devuelto permiso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
