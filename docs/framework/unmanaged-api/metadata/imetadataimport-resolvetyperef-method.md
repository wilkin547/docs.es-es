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
ms.openlocfilehash: 106ef520f64233323cbb3f26cb3efdee152559b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449486"
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
  
#### <a name="parameters"></a>Parámetros  
 `tr`  
 [in] Símbolo (token) de metadatos de TypeRef para devolver la información de tipo que se hace referencia.  
  
 `riid`  
 [in] El IID de la interfaz para devolver en `ppIScope`. Normalmente, esto sería IID_IMetaDataImport.  
  
 `ppIScope`  
 [out] Una interfaz para el ámbito del módulo en el que se define el tipo de referencia.  
  
 `ptd`  
 [out] Un puntero a un token de TypeDef que representa el tipo que se hace referencia.  
  
## <a name="remarks"></a>Comentarios  
  
> [!IMPORTANT]
>  No utilice este método si se cargan varios dominios de aplicación. El método no respeta los límites del dominio de aplicación. Si se cargan varias versiones de un ensamblado y que contienen el mismo tipo con el mismo espacio de nombres, el método devuelve el ámbito del módulo del primer tipo que encuentre.  
  
 El `ResolveTypeRef` método busca la definición de tipo en otros módulos. Si se encuentra la definición de tipo, `ResolveTypeRef` devuelve una interfaz para ese ámbito de módulo, así como el token de TypeDef para el tipo.  
  
 Si la referencia de tipo para que se resuelvan tiene un ámbito de resolución AssemblyRef, el `ResolveTypeRef` método busca una coincidencia sólo en los ámbitos de metadatos que ya se ha abierto con llamadas a la [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)método o la [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) método. Esto es porque `ResolveTypeRef` no se puede determinar desde únicamente al ámbito de AssemblyRef donde en el disco o en la caché global de ensamblados se almacena el ensamblado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
