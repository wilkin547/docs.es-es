---
description: 'Más información sobre: interfaz ICorPublishProcess'
title: ICorPublishProcess (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
ms.openlocfilehash: 8dbc619d33c2c9b625dde852948dff00b5be926e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800882"
---
# <a name="icorpublishprocess-interface"></a>ICorPublishProcess (Interfaz)

Proporciona métodos que tienen acceso a la información que se va a mostrar sobre un proceso.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EnumAppDomains](icorpublishprocess-enumappdomains-method.md)|Obtiene una instancia de [ICorPublishAppDomainEnum (](icorpublishappdomainenum-interface.md) que contiene los dominios de aplicación en el proceso al que hace referencia este `ICorPublishProcess` .|  
|[Método GetDisplayName](icorpublishprocess-getdisplayname-method.md)|Obtiene la ruta de acceso completa del archivo ejecutable para el proceso al que hace referencia este `ICorPublishProcess` .|  
|[Método GetProcessID](icorpublishprocess-getprocessid-method.md)|Obtiene el identificador del sistema operativo para el proceso al que hace referencia este `ICorPublishProcess` .|  
|[Método IsManaged](icorpublishprocess-ismanaged-method.md)|Obtiene un valor que indica si se sabe que el proceso al que hace referencia esto `ICorPublishProcess` está ejecutando código administrado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
- [CorpubPublish (coclase)](corpubpublish-coclass.md)
