---
description: 'Más información acerca de: interfaz Iclrmetadatalocator ('
title: ICLRMetadataLocator (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
ms.openlocfilehash: 6e7fd45197294563e12da020379d1bd54b088698
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772628"
---
# <a name="iclrmetadatalocator-interface"></a>ICLRMetadataLocator (Interfaz)

Lo utiliza el nivel de servicios de acceso a datos para buscar metadatos de ensamblados en un proceso de destino.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetMetadata (método)](iclrmetadatalocator-getmetadata-method.md)|Recupera los metadatos de una imagen del proceso de destino.|  
  
## <a name="remarks"></a>Observaciones  

 El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto. Por ejemplo, la implementación de un proceso activo sería diferente de la de un volcado de memoria.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
