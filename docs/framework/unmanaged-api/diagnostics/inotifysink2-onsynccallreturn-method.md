---
title: INotifySink2::OnSyncCallReturn (Método)
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
ms.openlocfilehash: fe2db3df688f91ec6e1aadd8cc3bb43726e5c30f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719962"
---
# <a name="inotifysink2onsynccallreturn-method"></a>INotifySink2::OnSyncCallReturn (Método)

Se invoca cuando se devuelve una llamada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `in_CallID`  
 de IDENTIFICADOR de la llamada que se devuelve desde. Vea [estructura de CALL_ID](call-id-structure.md).  
  
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
