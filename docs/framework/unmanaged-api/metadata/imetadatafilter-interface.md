---
title: IMetaDataFilter (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e1975a5063217299ddbcdce6f625d5a1285d5b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642560"
---
# <a name="imetadatafilter-interface"></a>IMetaDataFilter (Interfaz)
Proporciona métodos para marcar y filtrar los tokens de metadatos para evitar repetir acciones que ya se han realizado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[IsTokenMarked (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|Obtiene un valor que indica si se ha procesado el token de metadatos especificado.|  
|[MarkToken (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|Establece un valor que indica que se ha procesado el token de metadatos especificado.|  
|[UnmarkAll (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|Quita las marcas de procesamiento de todos los tokens en el ámbito de metadatos actual.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
