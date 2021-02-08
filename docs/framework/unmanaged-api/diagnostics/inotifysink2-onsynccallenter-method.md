---
description: 'Más información sobre: INotifySink2:: Onsynccallenter ((método)'
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
ms.openlocfilehash: e7537b16ec8ea8d92ad92498c1bfdac5a9de6475
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800284"
---
# <a name="inotifysink2onsynccallenter-method"></a><span data-ttu-id="0dc26-103">INotifySink2::OnSyncCallEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="0dc26-103">INotifySink2::OnSyncCallEnter Method</span></span>

<span data-ttu-id="0dc26-104">Se invoca al entrar en una llamada.</span><span class="sxs-lookup"><span data-stu-id="0dc26-104">Gets invoked when entering a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dc26-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0dc26-105">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dc26-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0dc26-106">Parameters</span></span>  

 `in_CallID`  
 <span data-ttu-id="0dc26-107">de IDENTIFICADOR de la llamada que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="0dc26-107">[in] ID of the call being entered.</span></span> <span data-ttu-id="0dc26-108">Vea [estructura de CALL_ID](call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="0dc26-108">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="0dc26-109">de Búfer de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0dc26-109">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="0dc26-110">de Tamaño del búfer de llamadas, en bytes.</span><span class="sxs-lookup"><span data-stu-id="0dc26-110">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0dc26-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0dc26-111">Return Value</span></span>  

 <span data-ttu-id="0dc26-112">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="0dc26-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dc26-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0dc26-113">Requirements</span></span>  

 <span data-ttu-id="0dc26-114">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="0dc26-114">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc26-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0dc26-115">See also</span></span>

- [<span data-ttu-id="0dc26-116">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0dc26-116">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="0dc26-117">INotifySource2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0dc26-117">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="0dc26-118">INotifyConnection2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0dc26-118">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
