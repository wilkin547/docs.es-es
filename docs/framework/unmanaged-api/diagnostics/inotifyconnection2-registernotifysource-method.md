---
description: 'Más información sobre: INotifyConnection2:: Registernotifysource ((método)'
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
ms.openlocfilehash: 97aacf7f2005a1e9f21acebd6c5f5ed65867b245
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800323"
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="0f414-103">INotifyConnection2::RegisterNotifySource (Método)</span><span class="sxs-lookup"><span data-stu-id="0f414-103">INotifyConnection2::RegisterNotifySource Method</span></span>

<span data-ttu-id="0f414-104">Instala un origen de notificación especificado.</span><span class="sxs-lookup"><span data-stu-id="0f414-104">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f414-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f414-105">Syntax</span></span>  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f414-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f414-106">Parameters</span></span>  

 `in_pNotifySource`  
 <span data-ttu-id="0f414-107">de Especifica el objeto que se va a usar como origen de la notificación.</span><span class="sxs-lookup"><span data-stu-id="0f414-107">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="0f414-108">enuncia Recibe el objeto que se va a usar como receptor de la notificación.</span><span class="sxs-lookup"><span data-stu-id="0f414-108">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f414-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0f414-109">Return Value</span></span>  

 <span data-ttu-id="0f414-110">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f414-110">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f414-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f414-111">Requirements</span></span>  

 <span data-ttu-id="0f414-112">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="0f414-112">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f414-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f414-113">See also</span></span>

- [<span data-ttu-id="0f414-114">INotifyConnection2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f414-114">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="0f414-115">INotifySource2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f414-115">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="0f414-116">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f414-116">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="0f414-117">Método UnregisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="0f414-117">UnregisterNotifySource Method</span></span>](inotifyconnection2-unregisternotifysource-method.md)
