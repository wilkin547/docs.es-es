---
title: ISymUnmanagedWriter2::DefineConstant2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c194cea21901015153626dc5aead49ed1b2c3df7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755114"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="38e5f-102">ISymUnmanagedWriter2::DefineConstant2 (Método)</span><span class="sxs-lookup"><span data-stu-id="38e5f-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="38e5f-103">Define un nombre para un valor constante.</span><span class="sxs-lookup"><span data-stu-id="38e5f-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38e5f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38e5f-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38e5f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="38e5f-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="38e5f-106">[in] El nombre de constante.</span><span class="sxs-lookup"><span data-stu-id="38e5f-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="38e5f-107">[in] El valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="38e5f-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="38e5f-108">[in] El token de metadatos de la constante.</span><span class="sxs-lookup"><span data-stu-id="38e5f-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38e5f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="38e5f-109">Return Value</span></span>  
 <span data-ttu-id="38e5f-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="38e5f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38e5f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38e5f-111">Requirements</span></span>  
 <span data-ttu-id="38e5f-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="38e5f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38e5f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="38e5f-113">See also</span></span>

- [<span data-ttu-id="38e5f-114">ISymUnmanagedWriter2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="38e5f-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="38e5f-115">DefineConstant (método)</span><span class="sxs-lookup"><span data-stu-id="38e5f-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
