---
title: IMetaDataDispenserEx (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d930088d6e621885d14fc4bdab2475aa27594e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448705"
---
# <a name="imetadatadispenserex-interface"></a>IMetaDataDispenserEx (Interfaz)
Extiende la [IMetaDataDispenser (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interfaz para proporcionar la capacidad para controlar el funcionamiento de las API de metadatos en el ámbito de metadatos actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[FindAssembly (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|Este método no se implementa. Si se llama, devuelve E_NOTIMPL.|  
|[FindAssemblyModule (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|Este método no se implementa. Si se llama, devuelve E_NOTIMPL.|  
|[GetCORSystemDirectory (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|Obtiene el directorio que contiene actual common language runtime (CLR). Este método es compatible únicamente para su uso con depuradores fuera de proceso. Si se llama desde otro componente, devolverá E_NOTIMPL.|  
|[GetOption (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|Obtiene el valor de la opción especificada para el ámbito de metadatos actual. La opción controla cómo se administran las llamadas al ámbito de metadatos actual.|  
|[OpenScopeOnITypeInfo (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|Este método no se implementa. Si se llama, devuelve E_NOTIMPL.|  
|[SetOption (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|Establece la opción especificada en un valor determinado para el ámbito de metadatos actual. La opción controla cómo se administran las llamadas al ámbito de metadatos actual.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataDispenser (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
