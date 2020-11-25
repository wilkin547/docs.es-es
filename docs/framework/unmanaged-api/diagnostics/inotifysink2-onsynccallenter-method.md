---
title: INotifySink2::OnSyncCallEnter (Método)
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallEnter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type:
- apiref
ms.openlocfilehash: 57d12a463bc0904e1a5c873d24f843e004b95101
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720014"
---
# <a name="inotifysink2onsynccallenter-method"></a>INotifySink2::OnSyncCallEnter (Método)

Se invoca al entrar en una llamada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `in_CallID`  
 de IDENTIFICADOR de la llamada que se va a escribir. Vea [estructura de CALL_ID](call-id-structure.md).  
  
 `in_pBuffer`  
 de Búfer de llamadas.  
  
 `in_BufferSize`  
 de Tamaño del búfer de llamadas, en bytes.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Consulte también

- [INotifySink2 (Interfaz)](inotifysink2-interface.md)
- [INotifySource2 (Interfaz)](inotifysource2-interface.md)
- [INotifyConnection2 (Interfaz)](inotifyconnection2-interface.md)
