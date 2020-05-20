---
title: INotifyConnection2::UnregisterNotifySource (Método)
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
ms.openlocfilehash: 9d0fcdcd4fe1561f7565586e3327c6d3d7e0fe0a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442051"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a>INotifyConnection2::UnregisterNotifySource (Método)
Quita un objeto de origen de notificación especificado de la conexión.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `in_pNotifySource`  
 de Objeto de notificación cuya registro se va a anular.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Consulta también

- [INotifyConnection2 (Interfaz)](inotifyconnection2-interface.md)
- [INotifySource2 (Interfaz)](inotifysource2-interface.md)
- [INotifySink2 (Interfaz)](inotifysink2-interface.md)
- [Método RegisterNotifySource](inotifyconnection2-registernotifysource-method.md)
