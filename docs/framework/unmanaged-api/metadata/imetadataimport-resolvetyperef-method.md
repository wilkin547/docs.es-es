---
description: 'Más información sobre: IMetaDataImport:: Resolvetyperef ((método)'
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
ms.openlocfilehash: 0634bac77f457432948d0c2887d676e95430d05d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677568"
---
# <a name="imetadataimportresolvetyperef-method"></a>IMetaDataImport::ResolveTypeRef (Método)

Resuelve una <xref:System.Type> referencia representada por el token TypeRef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `tr`  
 de Token de metadatos de TypeRef para el que se va a devolver la información de tipos a la que se hace referencia.  
  
 `riid`  
 de IID de la interfaz que se va a devolver en `ppIScope` . Normalmente, esto sería IID_IMetaDataImport.  
  
 `ppIScope`  
 enuncia Interfaz al ámbito del módulo en el que se define el tipo al que se hace referencia.  
  
 `ptd`  
 enuncia Un puntero a un token de TypeDef que representa el tipo al que se hace referencia.  
  
## <a name="remarks"></a>Observaciones  
  
> [!IMPORTANT]
> No use este método si se cargan varios dominios de aplicación. El método no respeta los límites del dominio de aplicación. Si se cargan varias versiones de un ensamblado y contienen el mismo tipo con el mismo espacio de nombres, el método devuelve el ámbito del módulo del primer tipo que encuentra.  
  
 El `ResolveTypeRef` método busca la definición de tipo en otros módulos. Si se encuentra la definición de tipo, `ResolveTypeRef` devuelve una interfaz a ese ámbito de módulo, así como el token de TypeDef para el tipo.  
  
 Si la referencia de tipo que se va a resolver tiene un ámbito de resolución de AssemblyRef, el `ResolveTypeRef` método busca una coincidencia solo en los ámbitos de metadatos que ya se han abierto con llamadas al método [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) o al método [IMetaDataDispenser:: openscopeonmemory (](imetadatadispenser-openscopeonmemory-method.md) . Esto se debe `ResolveTypeRef` a que no puede determinar solo el ámbito de AssemblyRef en el que se almacena en el disco o en la caché global de ensamblados el ensamblado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
