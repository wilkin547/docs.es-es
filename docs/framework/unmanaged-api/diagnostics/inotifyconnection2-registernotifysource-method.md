---
title: INotifyConnection2::RegisterNotifySource (Método)
ms.date: 03/30/2017
api_name:
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
ms.openlocfilehash: 1286dd970e437af0a8b607ed050ab4838f73a41f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720053"
---
# <a name="inotifyconnection2registernotifysource-method"></a>INotifyConnection2::RegisterNotifySource (Método)

Instala un origen de notificación especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `in_pNotifySource`  
 de Especifica el objeto que se va a usar como origen de la notificación.  
  
 `out_ppNotifySink`  
 enuncia Recibe el objeto que se va a usar como receptor de la notificación.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Consulte también

- [INotifyConnection2 (Interfaz)](inotifyconnection2-interface.md)
- [INotifySource2 (Interfaz)](inotifysource2-interface.md)
- [INotifySink2 (Interfaz)](inotifysink2-interface.md)
- [Método UnregisterNotifySource](inotifyconnection2-unregisternotifysource-method.md)
