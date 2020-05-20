---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 91b4c2688dadf12fa4a835a662622267d7831cf8
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441804"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="8d02e-102">ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="8d02e-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="8d02e-103">Comprueba si el método tiene información asincrónica o no.</span><span class="sxs-lookup"><span data-stu-id="8d02e-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="8d02e-104">Si este método devuelve `FALSE` , no es válido llamar a ningún otro método de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="8d02e-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="8d02e-105">En este caso, todos devolverán `E_UNEXPECTED` .</span><span class="sxs-lookup"><span data-stu-id="8d02e-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d02e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d02e-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d02e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d02e-107">Parameters</span></span>  
  
|<span data-ttu-id="8d02e-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="8d02e-108">Parameter</span></span>|<span data-ttu-id="8d02e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d02e-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="8d02e-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8d02e-110">Return Value</span></span>  
 <span data-ttu-id="8d02e-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="8d02e-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d02e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d02e-112">Requirements</span></span>  
 <span data-ttu-id="8d02e-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8d02e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d02e-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="8d02e-114">See also</span></span>

- [<span data-ttu-id="8d02e-115">ISymUnmanagedAsyncMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d02e-115">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
