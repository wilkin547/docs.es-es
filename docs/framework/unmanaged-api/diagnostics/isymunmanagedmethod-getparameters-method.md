---
title: ISymUnmanagedMethod::GetParameters (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetParameters
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a757e3b28a94c96e28a5bab736a6820a83617a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101235"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="1f62d-102">ISymUnmanagedMethod::GetParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="1f62d-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="1f62d-103">Obtiene los parámetros de este método.</span><span class="sxs-lookup"><span data-stu-id="1f62d-103">Gets the parameters for this method.</span></span> <span data-ttu-id="1f62d-104">Los parámetros se devuelven en el orden en que se definen dentro de la firma del método.</span><span class="sxs-lookup"><span data-stu-id="1f62d-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f62d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f62d-105">Syntax</span></span>  
  
```  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f62d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1f62d-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="1f62d-107">[in] Tamaño de la matriz `params`.</span><span class="sxs-lookup"><span data-stu-id="1f62d-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="1f62d-108">[in] Un puntero a un `ULONG32` que recibe el tamaño del búfer que es necesario para contener los parámetros.</span><span class="sxs-lookup"><span data-stu-id="1f62d-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="1f62d-109">[out] Un puntero al búfer que recibe los parámetros.</span><span class="sxs-lookup"><span data-stu-id="1f62d-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f62d-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1f62d-110">Return Value</span></span>  
 <span data-ttu-id="1f62d-111">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1f62d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f62d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f62d-112">Requirements</span></span>  
 <span data-ttu-id="1f62d-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1f62d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f62d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f62d-114">See also</span></span>

- [<span data-ttu-id="1f62d-115">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f62d-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
