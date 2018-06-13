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
ms.openlocfilehash: 2fbedb7b1c10dcc2b9b9940db10aae7e4101436b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426216"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="2944e-102">ISymUnmanagedMethod::GetParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="2944e-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="2944e-103">Obtiene los parámetros de este método.</span><span class="sxs-lookup"><span data-stu-id="2944e-103">Gets the parameters for this method.</span></span> <span data-ttu-id="2944e-104">Los parámetros se devuelven en el orden en que se definen dentro de la firma del método.</span><span class="sxs-lookup"><span data-stu-id="2944e-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2944e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2944e-105">Syntax</span></span>  
  
```  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2944e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2944e-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="2944e-107">[in] Tamaño de la matriz `params`.</span><span class="sxs-lookup"><span data-stu-id="2944e-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="2944e-108">[in] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los parámetros.</span><span class="sxs-lookup"><span data-stu-id="2944e-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="2944e-109">[out] Un puntero al búfer que recibe los parámetros.</span><span class="sxs-lookup"><span data-stu-id="2944e-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2944e-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2944e-110">Return Value</span></span>  
 <span data-ttu-id="2944e-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="2944e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2944e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2944e-112">Requirements</span></span>  
 <span data-ttu-id="2944e-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2944e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2944e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2944e-114">See Also</span></span>  
 [<span data-ttu-id="2944e-115">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2944e-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
