---
description: 'Más información sobre: ISymUnmanagedMethod:: GetParameters (método)'
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
ms.openlocfilehash: c8860a4d42019aaacef01879b175fd45ea837f2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721377"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="5e23e-103">ISymUnmanagedMethod::GetParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="5e23e-103">ISymUnmanagedMethod::GetParameters Method</span></span>

<span data-ttu-id="5e23e-104">Obtiene los parámetros de este método.</span><span class="sxs-lookup"><span data-stu-id="5e23e-104">Gets the parameters for this method.</span></span> <span data-ttu-id="5e23e-105">Los parámetros se devuelven en el orden en el que se definen dentro de la firma del método.</span><span class="sxs-lookup"><span data-stu-id="5e23e-105">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e23e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e23e-106">Syntax</span></span>  
  
```cpp  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e23e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5e23e-107">Parameters</span></span>  

 `cParams`  
 <span data-ttu-id="5e23e-108">[in] Tamaño de la matriz `params`.</span><span class="sxs-lookup"><span data-stu-id="5e23e-108">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="5e23e-109">de Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los parámetros.</span><span class="sxs-lookup"><span data-stu-id="5e23e-109">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="5e23e-110">enuncia Puntero al búfer que recibe los parámetros.</span><span class="sxs-lookup"><span data-stu-id="5e23e-110">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e23e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5e23e-111">Return Value</span></span>  

 <span data-ttu-id="5e23e-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="5e23e-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e23e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e23e-113">Requirements</span></span>  

 <span data-ttu-id="5e23e-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5e23e-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e23e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e23e-115">See also</span></span>

- [<span data-ttu-id="5e23e-116">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e23e-116">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
