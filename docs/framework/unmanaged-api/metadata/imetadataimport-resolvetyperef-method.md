---
title: IMetaDataImport::ResolveTypeRef (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f929e6b338d4fd48b2a6ef9588523377e0dd8faa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096067"
---
# <a name="imetadataimportresolvetyperef-method"></a>IMetaDataImport::ResolveTypeRef (Método)
Resuelve un <xref:System.Type> referencia representado por el símbolo (token) de TypeRef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `tr`  
 [in] El token de metadatos de TypeRef para devolver la información de tipo que se hace referencia.  
  
 `riid`  
 [in] El IID de la interfaz para devolver en `ppIScope`. Normalmente, esto sería IID_IMetaDataImport.  
  
 `ppIScope`  
 [out] Interfaz para el ámbito del módulo en el que se define el tipo que se hace referencia.  
  
 `ptd`  
 [out] Un puntero a un token de TypeDef que representa el tipo que se hace referencia.  
  
## <a name="remarks"></a>Comentarios  
  
> [!IMPORTANT]
>  No utilice este método si se cargan varios dominios de aplicación. El método no respeta los límites del dominio de aplicación. Si se cargan varias versiones de un ensamblado y contienen el mismo tipo con el mismo espacio de nombres, el método devuelve el ámbito del módulo del primer tipo que busca.  
  
 El `ResolveTypeRef` método busca la definición de tipo en otros módulos. Si se encuentra la definición de tipo, `ResolveTypeRef` devuelve una interfaz para ese ámbito de módulo, así como el token de TypeDef para el tipo.  
  
 Si se van a resolver la referencia de tipo tiene un ámbito de resolución AssemblyRef, el `ResolveTypeRef` método busca una coincidencia solo en los ámbitos de metadatos que ya se han abierto con las llamadas a la [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)método o la [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) método. Esto es porque `ResolveTypeRef` no se puede determinar desde únicamente al ámbito de AssemblyRef en disco o en la caché global de ensamblados el ensamblado se guarda.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
