---
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
ms.openlocfilehash: 8d958e949612b502ab218f5c6b75779174d34e19
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421090"
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
  
## <a name="see-also"></a>Consulta también

- [Interfaces para depuración](debugging-interfaces.md)
- [CorpubPublish (coclase)](corpubpublish-coclass.md)
