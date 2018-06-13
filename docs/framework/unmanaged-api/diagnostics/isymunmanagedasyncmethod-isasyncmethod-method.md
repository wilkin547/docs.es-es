---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f5bf8252986ffa90ea5380d5342595cb91e5419
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424946"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="52aae-102">ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="52aae-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="52aae-103">Comprueba si el método tiene información de async o no.</span><span class="sxs-lookup"><span data-stu-id="52aae-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="52aae-104">Si este método devuelve `FALSE` , a continuación, no es válido para llamar a ningún otro método en esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="52aae-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="52aae-105">Lo harían devuelven todos los `E_UNEXPECTED` en este caso.</span><span class="sxs-lookup"><span data-stu-id="52aae-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52aae-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52aae-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52aae-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52aae-107">Parameters</span></span>  
  
|<span data-ttu-id="52aae-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="52aae-108">Parameter</span></span>|<span data-ttu-id="52aae-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="52aae-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="52aae-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="52aae-110">Return Value</span></span>  
 <span data-ttu-id="52aae-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="52aae-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52aae-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52aae-112">Requirements</span></span>  
 <span data-ttu-id="52aae-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="52aae-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52aae-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="52aae-114">See Also</span></span>  
 [<span data-ttu-id="52aae-115">ISymUnmanagedAsyncMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="52aae-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
