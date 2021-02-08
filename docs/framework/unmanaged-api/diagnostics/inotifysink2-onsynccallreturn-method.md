---
description: 'Más información sobre: INotifySink2:: Onsynccallreturn ((método)'
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
ms.openlocfilehash: 01518de4e5a9e1374edddadb3c49f16e8fe679a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800258"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="1a5e7-103">INotifySink2::OnSyncCallReturn (Método)</span><span class="sxs-lookup"><span data-stu-id="1a5e7-103">INotifySink2::OnSyncCallReturn Method</span></span>

<span data-ttu-id="1a5e7-104">Se invoca cuando se devuelve una llamada.</span><span class="sxs-lookup"><span data-stu-id="1a5e7-104">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a5e7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a5e7-105">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a5e7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a5e7-106">Parameters</span></span>  

 `in_CallID`  
 <span data-ttu-id="1a5e7-107">de IDENTIFICADOR de la llamada que se devuelve desde.</span><span class="sxs-lookup"><span data-stu-id="1a5e7-107">[in] ID of the call being returned from.</span></span> <span data-ttu-id="1a5e7-108">Vea [estructura de CALL_ID](call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="1a5e7-108">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="1a5e7-109">de Búfer de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1a5e7-109">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="1a5e7-110">de Tamaño del búfer de llamadas, en bytes.</span><span class="sxs-lookup"><span data-stu-id="1a5e7-110">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a5e7-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1a5e7-111">Return Value</span></span>  

 <span data-ttu-id="1a5e7-112">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="1a5e7-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a5e7-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a5e7-113">Requirements</span></span>  

 <span data-ttu-id="1a5e7-114">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="1a5e7-114">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a5e7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a5e7-115">See also</span></span>

- [<span data-ttu-id="1a5e7-116">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a5e7-116">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="1a5e7-117">INotifySource2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a5e7-117">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="1a5e7-118">INotifyConnection2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a5e7-118">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
