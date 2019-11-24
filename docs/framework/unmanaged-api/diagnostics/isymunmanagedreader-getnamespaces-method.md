---
title: ISymUnmanagedReader::GetNamespaces (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type:
- apiref
ms.openlocfilehash: 458faedea418e626a6494ca2afcdbf0e034472e8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447734"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="ae614-102">ISymUnmanagedReader::GetNamespaces (Método)</span><span class="sxs-lookup"><span data-stu-id="ae614-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="ae614-103">Gets the namespaces defined at global scope within this symbol store.</span><span class="sxs-lookup"><span data-stu-id="ae614-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae614-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae614-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae614-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae614-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="ae614-106">[in] The size of the namespaces array.</span><span class="sxs-lookup"><span data-stu-id="ae614-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="ae614-107">[out] A pointer to a variable that receives the length of the namespace list.</span><span class="sxs-lookup"><span data-stu-id="ae614-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="ae614-108">[out] A pointer to a variable that receives the namespace list.</span><span class="sxs-lookup"><span data-stu-id="ae614-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae614-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ae614-109">Return Value</span></span>  
 <span data-ttu-id="ae614-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="ae614-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae614-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae614-111">Requirements</span></span>  
 <span data-ttu-id="ae614-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ae614-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae614-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae614-113">See also</span></span>

- [<span data-ttu-id="ae614-114">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae614-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
