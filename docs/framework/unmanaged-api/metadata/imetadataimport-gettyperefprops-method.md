---
title: IMetaDataImport::GetTypeRefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a4d8829c9cb2818eafe98809c9a0d5fd8109d076
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778825"
---
# <a name="imetadataimportgettyperefprops-method"></a>IMetaDataImport::GetTypeRefProps (Método)
Obtiene los metadatos asociados con el <xref:System.Type> al que hace referencia el token de TypeRef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `tr`  
 [in] Símbolo (token) de TypeRef que representa el tipo para devolver los metadatos.  
  
 `ptkResolutionScope`  
 [out] Un puntero en el ámbito en el que se hace la referencia. Este valor es un token AssemblyRef o ModuleRef.  
  
 `szName`  
 [out] Un búfer que contiene el nombre de tipo.  
  
 `cchName`  
 [in] El tamaño solicitado en caracteres anchos de `szName`.  
  
 `pchName`  
 [out] El tamaño devuelto en caracteres anchos de `szName`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
