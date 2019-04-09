---
title: IMetaDataImport::FindTypeDefByName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeDefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5cd6b74ce2871cfafc0dc2260be3f758f6a28704
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168693"
---
# <a name="imetadataimportfindtypedefbyname-method"></a>IMetaDataImport::FindTypeDefByName (Método)
Obtiene un puntero a los metadatos de TypeDef token para el <xref:System.Type> con el nombre especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `szTypeDef`  
 [in] El nombre del tipo para el que se va a obtener el token de la definición de tipo.  
  
 `tkEnclosingClass`  
 [in] Un token de TypeDef o TypeRef que representa la clase envolvente. Si el tipo de búsqueda no es una clase anidada, establezca este valor en NULL.  
  
 `ptd`  
 [out] Un puntero al token de TypeDef coincidente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
