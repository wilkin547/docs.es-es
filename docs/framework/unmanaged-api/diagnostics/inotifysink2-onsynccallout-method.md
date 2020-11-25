---
title: INotifySink2::OnSyncCallOut (Método)
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
ms.openlocfilehash: 00f6032f41caf54d7366de30a449f1ae76e8bbd0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719988"
---
# <a name="inotifysink2onsynccallout-method"></a>INotifySink2::OnSyncCallOut (Método)

Se invoca cuando se realiza una llamada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `in_CallID`  
 de IDENTIFICADOR de la llamada que está fuera. Vea [estructura de CALL_ID](call-id-structure.md).  
  
 `out_ppBuffer`  
 enuncia Búfer de llamadas.  
  
 `out_pBufferSize`  
 enuncia Tamaño del búfer de llamadas, en bytes.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Consulte también

- [INotifySink2 (Interfaz)](inotifysink2-interface.md)
- [INotifySource2 (Interfaz)](inotifysource2-interface.md)
- [INotifyConnection2 (Interfaz)](inotifyconnection2-interface.md)
