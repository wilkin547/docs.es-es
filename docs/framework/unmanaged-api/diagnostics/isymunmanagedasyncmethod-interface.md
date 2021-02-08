---
description: 'Más información acerca de: interfaz ISymUnmanagedAsyncMethod'
title: ISymUnmanagedAsyncMethod (Interfaz)
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: cb3120464224137dfdcff4f13ca4aee82ef4d89e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790274"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="dbf67-103">ISymUnmanagedAsyncMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dbf67-103">ISymUnmanagedAsyncMethod Interface</span></span>

<span data-ttu-id="dbf67-104">Esta interfaz es el complemento de lectura de la [interfaz ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="dbf67-104">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbf67-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbf67-105">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="dbf67-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="dbf67-106">Methods</span></span>  

 <span data-ttu-id="dbf67-107">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="dbf67-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="dbf67-108">Método</span><span class="sxs-lookup"><span data-stu-id="dbf67-108">Method</span></span>|<span data-ttu-id="dbf67-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="dbf67-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dbf67-110">Método GetAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="dbf67-110">GetAsyncStepInfo Method</span></span>](isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="dbf67-111">Consulte [método defineasyncstepinfo (](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="dbf67-111">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="dbf67-112">Método GetAsyncStepInfoCount</span><span class="sxs-lookup"><span data-stu-id="dbf67-112">GetAsyncStepInfoCount Method</span></span>](isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="dbf67-113">Consulte [método defineasyncstepinfo (](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="dbf67-113">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="dbf67-114">Método GetCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="dbf67-114">GetCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="dbf67-115">Consulte [método definecatchhandleriloffset (](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="dbf67-115">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="dbf67-116">Método GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="dbf67-116">GetKickoffMethod Method</span></span>](isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="dbf67-117">Consulte [método definekickoffmethod (](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="dbf67-117">See [DefineKickoffMethod Method](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="dbf67-118">Método HasCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="dbf67-118">HasCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="dbf67-119">Consulte [método definecatchhandleriloffset (](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="dbf67-119">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="dbf67-120">Método IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="dbf67-120">IsAsyncMethod Method</span></span>](isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="dbf67-121">Comprueba si el método tiene información asincrónica o no.</span><span class="sxs-lookup"><span data-stu-id="dbf67-121">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="dbf67-122">Si este método devuelve `FALSE` , no es válido llamar a ningún otro método de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="dbf67-122">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="dbf67-123">En este caso, todos devolverán `E_UNEXPECTED` .</span><span class="sxs-lookup"><span data-stu-id="dbf67-123">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dbf67-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dbf67-124">Requirements</span></span>  

 <span data-ttu-id="dbf67-125">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="dbf67-125">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf67-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbf67-126">See also</span></span>

- [<span data-ttu-id="dbf67-127">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="dbf67-127">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
