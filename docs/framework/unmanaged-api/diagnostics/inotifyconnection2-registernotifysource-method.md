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
ms.openlocfilehash: b7fa777466e2c7edd7b3110dd91e776785c63c58
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442077"
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="43cba-102">INotifyConnection2::RegisterNotifySource (Método)</span><span class="sxs-lookup"><span data-stu-id="43cba-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="43cba-103">Instala un origen de notificación especificado.</span><span class="sxs-lookup"><span data-stu-id="43cba-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43cba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43cba-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43cba-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43cba-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="43cba-106">de Especifica el objeto que se va a usar como origen de la notificación.</span><span class="sxs-lookup"><span data-stu-id="43cba-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="43cba-107">enuncia Recibe el objeto que se va a usar como receptor de la notificación.</span><span class="sxs-lookup"><span data-stu-id="43cba-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43cba-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="43cba-108">Return Value</span></span>  
 <span data-ttu-id="43cba-109">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="43cba-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43cba-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43cba-110">Requirements</span></span>  
 <span data-ttu-id="43cba-111">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="43cba-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43cba-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="43cba-112">See also</span></span>

- [<span data-ttu-id="43cba-113">INotifyConnection2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="43cba-113">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="43cba-114">INotifySource2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="43cba-114">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="43cba-115">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="43cba-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="43cba-116">Método UnregisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="43cba-116">UnregisterNotifySource Method</span></span>](inotifyconnection2-unregisternotifysource-method.md)
