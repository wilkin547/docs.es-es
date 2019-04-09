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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9dac5ae2f0f77c7b6d2dbd7f908f3552823735b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109608"
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="83d90-102">INotifyConnection2::RegisterNotifySource (Método)</span><span class="sxs-lookup"><span data-stu-id="83d90-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="83d90-103">Instala un origen de notificación especificado.</span><span class="sxs-lookup"><span data-stu-id="83d90-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d90-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83d90-104">Syntax</span></span>  
  
```  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83d90-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83d90-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="83d90-106">[in] Especifica el objeto que se usará como origen de notificación.</span><span class="sxs-lookup"><span data-stu-id="83d90-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="83d90-107">[out] Recibe el objeto que se usará como el receptor de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="83d90-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83d90-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="83d90-108">Return Value</span></span>  
 <span data-ttu-id="83d90-109">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="83d90-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83d90-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83d90-110">Requirements</span></span>  
 <span data-ttu-id="83d90-111">**Encabezado**: ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="83d90-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d90-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="83d90-112">See also</span></span>

- [<span data-ttu-id="83d90-113">INotifyConnection2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83d90-113">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="83d90-114">INotifySource2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83d90-114">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="83d90-115">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83d90-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="83d90-116">Método UnregisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="83d90-116">UnregisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-unregisternotifysource-method.md)
