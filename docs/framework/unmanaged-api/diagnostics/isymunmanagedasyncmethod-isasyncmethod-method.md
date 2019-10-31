---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 0ea4c21e9e6a49d7bbbad5e1853598c440cd6410
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129211"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="f715d-102">ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="f715d-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="f715d-103">Comprueba si el método tiene información asincrónica o no.</span><span class="sxs-lookup"><span data-stu-id="f715d-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="f715d-104">Si este método devuelve `FALSE`, no es válido llamar a ningún otro método de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="f715d-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="f715d-105">Todos devolverán `E_UNEXPECTED` en este caso.</span><span class="sxs-lookup"><span data-stu-id="f715d-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f715d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f715d-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f715d-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f715d-107">Parameters</span></span>  
  
|<span data-ttu-id="f715d-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="f715d-108">Parameter</span></span>|<span data-ttu-id="f715d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f715d-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="f715d-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f715d-110">Return Value</span></span>  
 <span data-ttu-id="f715d-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="f715d-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f715d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f715d-112">Requirements</span></span>  
 <span data-ttu-id="f715d-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f715d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f715d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f715d-114">See also</span></span>

- [<span data-ttu-id="f715d-115">ISymUnmanagedAsyncMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f715d-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
