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
ms.openlocfilehash: 76514cfbd2e533f04c5139dbaef4429c12463106
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445474"
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="0025a-102">INotifyConnection2::RegisterNotifySource (Método)</span><span class="sxs-lookup"><span data-stu-id="0025a-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="0025a-103">Instala un origen de notificación especificado.</span><span class="sxs-lookup"><span data-stu-id="0025a-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0025a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0025a-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0025a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0025a-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="0025a-106">de Especifica el objeto que se va a usar como origen de la notificación.</span><span class="sxs-lookup"><span data-stu-id="0025a-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="0025a-107">enuncia Recibe el objeto que se va a usar como receptor de la notificación.</span><span class="sxs-lookup"><span data-stu-id="0025a-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0025a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0025a-108">Return Value</span></span>  
 <span data-ttu-id="0025a-109">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="0025a-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0025a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0025a-110">Requirements</span></span>  
 <span data-ttu-id="0025a-111">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="0025a-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0025a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0025a-112">See also</span></span>

- [<span data-ttu-id="0025a-113">INotifyConnection2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0025a-113">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="0025a-114">INotifySource2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0025a-114">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="0025a-115">INotifySink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0025a-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="0025a-116">UnregisterNotifySource (método)</span><span class="sxs-lookup"><span data-stu-id="0025a-116">UnregisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-unregisternotifysource-method.md)
