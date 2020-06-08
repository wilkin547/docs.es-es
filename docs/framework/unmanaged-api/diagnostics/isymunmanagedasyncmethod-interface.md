---
title: ISymUnmanagedAsyncMethod (Interfaz)
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: 448ed719331469dce8f15500f14d5c1b0707ecf7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504457"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="9c39f-102">ISymUnmanagedAsyncMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c39f-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="9c39f-103">Esta interfaz es el complemento de lectura de la [interfaz ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9c39f-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c39f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c39f-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="9c39f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="9c39f-105">Methods</span></span>  
 <span data-ttu-id="9c39f-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="9c39f-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="9c39f-107">Método</span><span class="sxs-lookup"><span data-stu-id="9c39f-107">Method</span></span>|<span data-ttu-id="9c39f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c39f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9c39f-109">Método GetAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="9c39f-109">GetAsyncStepInfo Method</span></span>](isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="9c39f-110">Consulte [método defineasyncstepinfo (](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="9c39f-110">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="9c39f-111">Método GetAsyncStepInfoCount</span><span class="sxs-lookup"><span data-stu-id="9c39f-111">GetAsyncStepInfoCount Method</span></span>](isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="9c39f-112">Consulte [método defineasyncstepinfo (](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="9c39f-112">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="9c39f-113">Método GetCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="9c39f-113">GetCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="9c39f-114">Consulte [método definecatchhandleriloffset (](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="9c39f-114">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="9c39f-115">Método GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="9c39f-115">GetKickoffMethod Method</span></span>](isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="9c39f-116">Consulte [método definekickoffmethod (](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="9c39f-116">See [DefineKickoffMethod Method](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="9c39f-117">Método HasCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="9c39f-117">HasCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="9c39f-118">Consulte [método definecatchhandleriloffset (](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="9c39f-118">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="9c39f-119">Método IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="9c39f-119">IsAsyncMethod Method</span></span>](isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="9c39f-120">Comprueba si el método tiene información asincrónica o no.</span><span class="sxs-lookup"><span data-stu-id="9c39f-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="9c39f-121">Si este método devuelve `FALSE` , no es válido llamar a ningún otro método de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="9c39f-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="9c39f-122">En este caso, todos devolverán `E_UNEXPECTED` .</span><span class="sxs-lookup"><span data-stu-id="9c39f-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9c39f-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c39f-123">Requirements</span></span>  
 <span data-ttu-id="9c39f-124">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9c39f-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c39f-125">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="9c39f-125">See also</span></span>

- [<span data-ttu-id="9c39f-126">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="9c39f-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
