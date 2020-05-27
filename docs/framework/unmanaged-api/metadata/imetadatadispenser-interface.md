---
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
ms.openlocfilehash: 2bdfe65dbf923ec61d91a259b5257d892fef53da
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007343"
---
# <a name="imetadatadispenser-interface"></a>IMetaDataDispenser (Interfaz)
Proporciona métodos para crear un nuevo ámbito de metadatos o abrir uno existente.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método DefineScope](imetadatadispenser-definescope-method.md)|Crea un nuevo área en la memoria donde se pueden crear nuevos metadatos.|  
|[Método OpenScope](imetadatadispenser-openscope-method.md)|Abre un archivo en disco existente y asigna sus metadatos a la memoria.|  
|[Método OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md)|Abre un área de memoria que contiene los metadatos existentes. Es decir, este método abre un área de memoria especificada en la que los datos existentes se tratan como metadatos.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataDispenserEx (Interfaz)](imetadatadispenserex-interface.md)
- [Interfaces de metadatos](metadata-interfaces.md)
