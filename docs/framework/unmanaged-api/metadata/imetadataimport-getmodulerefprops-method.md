---
description: 'Más información sobre: IMetaDataImport:: GetModuleRefProps ((método)'
title: IMetaDataImport::GetModuleRefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type:
- apiref
ms.openlocfilehash: 3e6b212ddad5eefb06942c3fd4b89411b277f761
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753359"
---
# <a name="imetadataimportgetmodulerefprops-method"></a>IMetaDataImport::GetModuleRefProps (Método)

Obtiene el nombre del módulo al que hace referencia el token de metadatos especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,
   [in]  ULONG               cchName,
   [out] ULONG               *pchName
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `mur`  
 de Token de metadatos de ModuleRef que hace referencia al módulo para el que se va a obtener información de metadatos.  
  
 `szName`  
 enuncia Búfer que contiene el nombre del módulo.  
  
 `cchName`  
 de Tamaño solicitado de `szName` caracteres anchos.  
  
 `pchName`  
 enuncia Tamaño devuelto de `szName` en caracteres anchos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
