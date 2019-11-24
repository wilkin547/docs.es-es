---
title: ISymUnmanagedWriter::CloseNamespace (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
ms.openlocfilehash: b29e66a4e124f6d593fc0c8aed9a63fcc660f8df
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428091"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="45d1a-102">ISymUnmanagedWriter::CloseNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="45d1a-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="45d1a-103">Closes the most recently opened namespace.</span><span class="sxs-lookup"><span data-stu-id="45d1a-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45d1a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45d1a-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="45d1a-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="45d1a-105">Return Value</span></span>  
 <span data-ttu-id="45d1a-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="45d1a-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45d1a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45d1a-107">Requirements</span></span>  
 <span data-ttu-id="45d1a-108">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="45d1a-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d1a-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="45d1a-109">See also</span></span>

- [<span data-ttu-id="45d1a-110">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="45d1a-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="45d1a-111">OpenNamespace (método)</span><span class="sxs-lookup"><span data-stu-id="45d1a-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)
