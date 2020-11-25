---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: af02aba1a0d390c103e8c6108f90b93fe2a98ff3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707157"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="f17e0-102">ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="f17e0-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>

<span data-ttu-id="f17e0-103">Comprueba si el método tiene información asincrónica o no.</span><span class="sxs-lookup"><span data-stu-id="f17e0-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="f17e0-104">Si este método devuelve `FALSE` , no es válido llamar a ningún otro método de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="f17e0-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="f17e0-105">En este caso, todos devolverán `E_UNEXPECTED` .</span><span class="sxs-lookup"><span data-stu-id="f17e0-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f17e0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f17e0-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f17e0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f17e0-107">Parameters</span></span>  
  
|<span data-ttu-id="f17e0-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="f17e0-108">Parameter</span></span>|<span data-ttu-id="f17e0-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f17e0-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="f17e0-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f17e0-110">Return Value</span></span>  

 <span data-ttu-id="f17e0-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="f17e0-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f17e0-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f17e0-112">Requirements</span></span>  

 <span data-ttu-id="f17e0-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f17e0-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f17e0-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f17e0-114">See also</span></span>

- [<span data-ttu-id="f17e0-115">ISymUnmanagedAsyncMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f17e0-115">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
