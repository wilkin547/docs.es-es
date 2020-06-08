---
title: IMetaDataImport::GetScopeProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
ms.openlocfilehash: 0916b6382bb9352616d85e21f423301dc6aa9fa9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490853"
---
# <a name="imetadataimportgetscopeprops-method"></a>IMetaDataImport::GetScopeProps (Método)
Obtiene el nombre y, si quiere, el identificador de versión del ensamblado o el módulo en el ámbito de metadatos actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `szName`  
 enuncia Búfer del nombre del ensamblado o del módulo.  
  
 `cchName`  
 de Tamaño en caracteres anchos de `szName` .  
  
 `pchName`  
 enuncia Número de caracteres anchos devueltos en `szName` .  
  
 `pmvid`  
 [out, opcional] Un puntero a un GUID que identifica de forma única la versión del ensamblado o módulo.  
  
## <a name="remarks"></a>Comentarios  
 El método [IMetaDataEmit:: SetModuleProps (](imetadataemit-setmoduleprops-method.md) se usa para establecer estas propiedades.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
