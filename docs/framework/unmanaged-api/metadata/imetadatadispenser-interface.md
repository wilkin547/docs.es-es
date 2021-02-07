---
description: 'Más información acerca de: IMetaDataDispenser (interfaz)'
title: IMetaDataDispenser (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
ms.openlocfilehash: 5ba37fc05a4e1897b100967d32b268f91a0e4402
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721013"
---
# <a name="imetadatadispenser-interface"></a>IMetaDataDispenser (Interfaz)

Proporciona métodos para crear un nuevo ámbito de metadatos o abrir uno existente.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método DefineScope](imetadatadispenser-definescope-method.md)|Crea un nuevo área en la memoria donde se pueden crear nuevos metadatos.|  
|[OpenScope (Método)](imetadatadispenser-openscope-method.md)|Abre un archivo en disco existente y asigna sus metadatos a la memoria.|  
|[Método OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md)|Abre un área de memoria que contiene los metadatos existentes. Es decir, este método abre un área de memoria especificada en la que los datos existentes se tratan como metadatos.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataDispenserEx (Interfaz)](imetadatadispenserex-interface.md)
- [Interfaces de metadatos](metadata-interfaces.md)
