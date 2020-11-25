---
title: ISymUnmanagedWriter::DefineConstant (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
ms.openlocfilehash: 7c4589c3371d2c66279684a365cde102bef58c6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727593"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="efe80-102">ISymUnmanagedWriter::DefineConstant (Método)</span><span class="sxs-lookup"><span data-stu-id="efe80-102">ISymUnmanagedWriter::DefineConstant Method</span></span>

<span data-ttu-id="efe80-103">Define un nombre para un valor constante.</span><span class="sxs-lookup"><span data-stu-id="efe80-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efe80-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efe80-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efe80-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="efe80-105">Parameters</span></span>  

 `name`  
 <span data-ttu-id="efe80-106">de Puntero a `WCHAR` que define el nombre de la constante.</span><span class="sxs-lookup"><span data-stu-id="efe80-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="efe80-107">de Valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="efe80-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="efe80-108">[in] Tamaño de la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="efe80-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="efe80-109">de Firma de tipo de la constante.</span><span class="sxs-lookup"><span data-stu-id="efe80-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efe80-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="efe80-110">Return Value</span></span>  

 <span data-ttu-id="efe80-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="efe80-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efe80-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="efe80-112">Requirements</span></span>  

 <span data-ttu-id="efe80-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="efe80-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efe80-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="efe80-114">See also</span></span>

- [<span data-ttu-id="efe80-115">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="efe80-115">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="efe80-116">Método DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="efe80-116">DefineConstant2 Method</span></span>](isymunmanagedwriter2-defineconstant2-method.md)
