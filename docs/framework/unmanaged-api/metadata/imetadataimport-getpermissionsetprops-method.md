---
description: 'Más información sobre: IMetaDataImport:: Getpermissionsetprops ((método)'
title: IMetaDataImport::GetPermissionSetProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
ms.openlocfilehash: 9dc10b7bf531b6eec389334d80cf6a1cece20ee9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789195"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a>IMetaDataImport::GetPermissionSetProps (Método)

Obtiene los metadatos asociados al <xref:System.Security.PermissionSet?displayProperty=nameWithType> representado por el token de permiso especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pm`  
 de Token de metadatos de permiso que representa el conjunto de permisos para el que se van a obtener las propiedades de metadatos.  
  
 `pdwAction`  
 enuncia Puntero al conjunto de permisos.  
  
 `ppvPermission`  
 enuncia Puntero a la firma de metadatos binarios del conjunto de permisos.  
  
 `pcbPermission`  
 enuncia Tamaño en bytes de `ppvPermission` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Security.PermissionSet>
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
