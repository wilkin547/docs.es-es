---
title: puntero a la función FLockClrVersionCallback
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
ms.openlocfilehash: d18702a1bb15d2cc6c7b8577b91ed011e9bd0c05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733677"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="ca05f-102">puntero a la función FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="ca05f-102">FLockClrVersionCallback Function Pointer</span></span>

<span data-ttu-id="ca05f-103">Apunta a una función a la que llama el Common Language Runtime (CLR) para indicar que la inicialización se ha iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="ca05f-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="ca05f-104">Este puntero de función ha quedado en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ca05f-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca05f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca05f-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="ca05f-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca05f-106">Remarks</span></span>  

 <span data-ttu-id="ca05f-107">Esta función se implementa mediante el host.</span><span class="sxs-lookup"><span data-stu-id="ca05f-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca05f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca05f-108">Requirements</span></span>  

 <span data-ttu-id="ca05f-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca05f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca05f-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ca05f-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca05f-111">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="ca05f-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="ca05f-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca05f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca05f-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca05f-113">See also</span></span>

- [<span data-ttu-id="ca05f-114">LockClrVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="ca05f-114">LockClrVersion Function</span></span>](lockclrversion-function.md)
- [<span data-ttu-id="ca05f-115">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="ca05f-115">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
