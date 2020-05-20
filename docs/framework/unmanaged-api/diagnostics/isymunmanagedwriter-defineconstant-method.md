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
ms.openlocfilehash: 200e68abb3f176c267045bf2a5e7e35d18400519
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610098"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="bfcd3-102">ISymUnmanagedWriter::DefineConstant (Método)</span><span class="sxs-lookup"><span data-stu-id="bfcd3-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="bfcd3-103">Define un nombre para un valor constante.</span><span class="sxs-lookup"><span data-stu-id="bfcd3-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfcd3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfcd3-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfcd3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bfcd3-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="bfcd3-106">de Puntero a `WCHAR` que define el nombre de la constante.</span><span class="sxs-lookup"><span data-stu-id="bfcd3-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="bfcd3-107">de Valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="bfcd3-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="bfcd3-108">[in] Tamaño de la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="bfcd3-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="bfcd3-109">de Firma de tipo de la constante.</span><span class="sxs-lookup"><span data-stu-id="bfcd3-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfcd3-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bfcd3-110">Return Value</span></span>  
 <span data-ttu-id="bfcd3-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="bfcd3-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfcd3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bfcd3-112">Requirements</span></span>  
 <span data-ttu-id="bfcd3-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="bfcd3-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfcd3-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="bfcd3-114">See also</span></span>

- [<span data-ttu-id="bfcd3-115">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bfcd3-115">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="bfcd3-116">Método DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="bfcd3-116">DefineConstant2 Method</span></span>](isymunmanagedwriter2-defineconstant2-method.md)
