---
description: 'Más información sobre: ISymUnmanagedAsyncMethod:: Isasyncmethod ((método)'
title: ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 4b151f5367bac5fd92cc8237492cad6dacfb8e88
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790261"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="df9a5-103">ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="df9a5-103">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>

<span data-ttu-id="df9a5-104">Comprueba si el método tiene información asincrónica o no.</span><span class="sxs-lookup"><span data-stu-id="df9a5-104">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="df9a5-105">Si este método devuelve `FALSE` , no es válido llamar a ningún otro método de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="df9a5-105">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="df9a5-106">En este caso, todos devolverán `E_UNEXPECTED` .</span><span class="sxs-lookup"><span data-stu-id="df9a5-106">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df9a5-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df9a5-107">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df9a5-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df9a5-108">Parameters</span></span>  
  
|<span data-ttu-id="df9a5-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="df9a5-109">Parameter</span></span>|<span data-ttu-id="df9a5-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="df9a5-110">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="df9a5-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="df9a5-111">Return Value</span></span>  

 <span data-ttu-id="df9a5-112">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="df9a5-112">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df9a5-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df9a5-113">Requirements</span></span>  

 <span data-ttu-id="df9a5-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="df9a5-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df9a5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="df9a5-115">See also</span></span>

- [<span data-ttu-id="df9a5-116">ISymUnmanagedAsyncMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="df9a5-116">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
