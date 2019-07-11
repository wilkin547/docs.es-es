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
ms.openlocfilehash: 7d3c0d833208c91c548ea993bb6aa32e36e1f358
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776639"
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="4cc05-102">INotifyConnection2::RegisterNotifySource (Método)</span><span class="sxs-lookup"><span data-stu-id="4cc05-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="4cc05-103">Instala un origen de notificación especificado.</span><span class="sxs-lookup"><span data-stu-id="4cc05-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cc05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4cc05-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cc05-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4cc05-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="4cc05-106">[in] Especifica el objeto que se usará como origen de notificación.</span><span class="sxs-lookup"><span data-stu-id="4cc05-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="4cc05-107">[out] Recibe el objeto que se usará como el receptor de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="4cc05-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cc05-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4cc05-108">Return Value</span></span>  
 <span data-ttu-id="4cc05-109">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="4cc05-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cc05-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4cc05-110">Requirements</span></span>  
 <span data-ttu-id="4cc05-111">**Encabezado**: ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="4cc05-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc05-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cc05-112">See also</span></span>

- [<span data-ttu-id="4cc05-113">INotifyConnection2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cc05-113">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="4cc05-114">INotifySource2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cc05-114">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="4cc05-115">INotifySink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cc05-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="4cc05-116">UnregisterNotifySource (método)</span><span class="sxs-lookup"><span data-stu-id="4cc05-116">UnregisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-unregisternotifysource-method.md)
