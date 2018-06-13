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
ms.openlocfilehash: 05339787b112ad029cb9870e8c6ffca37e55e631
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445194"
---
# <a name="imetadataemitdefinepermissionset-method"></a>IMetaDataEmit::DefinePermissionSet (Método)
Crea una definición para un conjunto de permisos con la firma de metadatos especificada y obtiene un símbolo (token) para dicha definición de conjunto de permisos.  
  
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
  
#### <a name="parameters"></a>Parámetros  
 `tk`  
 [in] El objeto que va a ser representativo.  
  
 `dwAction`  
 [in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) valor que especifica el tipo de seguridad declarativa que se va a usar.  
  
 `pvPermission`  
 [in] El BLOB de permiso.  
  
 `cbPermission`  
 [in] El tamaño, en bytes, de `pvPermission`.  
  
 `ppm`  
 [out] El token de permiso devuelto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
