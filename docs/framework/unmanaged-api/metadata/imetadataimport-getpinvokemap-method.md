---
title: IMetaDataImport::GetPinvokeMap (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2aed3367e20e32a387c8a1c58ead2899fbf0dcb9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521444"
---
# <a name="imetadataimportgetpinvokemap-method"></a>IMetaDataImport::GetPinvokeMap (Método)
Obtiene un token ModuleRef para representar el ensamblado de destino de una llamada PInvoke.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `tk`  
 [in] Un token de FieldDef o MethodDef para obtener los metadatos de asignación de PInvoke.  
  
 `pdwMappingFlags`  
 [out] Un puntero a los marcadores utilizados para la asignación. Este valor es una máscara de bits desde el [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeración.  
  
 `szImportName`  
 [out] El nombre de la DLL de destino no administrado.  
  
 `cchImportName`  
 [in] El tamaño en caracteres anchos de `szImportName`.  
  
 `pchImportName`  
 [out] El número de caracteres anchos que se devuelven en `szImportName`.  
  
 `pmrImportDLL`  
 [out] Un puntero a un token ModuleRef que representa la biblioteca de objetos de destino no administrado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
