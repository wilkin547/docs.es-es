---
description: 'Más información acerca de: interfaz IMetaDataDispenserEx'
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
ms.openlocfilehash: d940ac20eaad4b930ab17fb2d194d3b03bd4cf3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753541"
---
# <a name="imetadatadispenserex-interface"></a>IMetaDataDispenserEx (Interfaz)

Extiende la interfaz [IMetaDataDispenser interface](imetadatadispenser-interface.md) para proporcionar la capacidad de controlar el funcionamiento de las API de metadatos en el ámbito de metadatos actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método FindAssembly](imetadatadispenserex-findassembly-method.md)|Este método no se implementa. Si se llama, devuelve E_NOTIMPL.|  
|[Método FindAssemblyModule](imetadatadispenserex-findassemblymodule-method.md)|Este método no se implementa. Si se llama, devuelve E_NOTIMPL.|  
|[Método GetCORSystemDirectory](imetadatadispenserex-getcorsystemdirectory-method.md)|Obtiene el directorio que contiene el Common Language Runtime actual (CLR). Este método solo se admite para su uso en depuradores fuera de proceso. Si se llama desde otro componente, devolverá E_NOTIMPL.|  
|[Método GetOption](imetadatadispenserex-getoption-method.md)|Obtiene el valor de la opción especificada para el ámbito de metadatos actual. La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.|  
|[Método OpenScopeOnITypeInfo](imetadatadispenserex-openscopeonitypeinfo-method.md)|Este método no se implementa. Si se llama, devuelve E_NOTIMPL.|  
|[Método SetOption](imetadatadispenserex-setoption-method.md)|Establece la opción especificada en un valor determinado para el ámbito de metadatos actual. La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](metadata-interfaces.md)
- [IMetaDataDispenser (Interfaz)](imetadatadispenser-interface.md)
- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
