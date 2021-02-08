---
description: 'Más información sobre: IMetaDataEmit:: Setpermissionsetprops ((método)'
title: IMetaDataEmit::SetPermissionSetProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
ms.openlocfilehash: 1e2786a21a1024f32328e36878a1a2427af54f51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771891"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a>IMetaDataEmit::SetPermissionSetProps (Método)

Establece o actualiza las características de la firma de metadatos de un conjunto de permisos definido por una llamada anterior a [IMetaDataEmit::D efinepermissionset](imetadataemit-definepermissionset-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `tk`  
 de Token de metadatos que representa el objeto que se va a decorar.  
  
 `dwAction`  
 de Valor [cordeclsecurity (](cordeclsecurity-enumeration.md) que especifica el tipo de seguridad declarativa que se va a utilizar.  
  
 `pvPermission`  
 de El BLOB de permiso.  
  
 `cbPermission`  
 de Tamaño, en bytes, de `pvPermission` .  
  
 `ppm`  
 enuncia `mdPermission` Token de metadatos que representa los permisos actualizados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
