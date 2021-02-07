---
description: 'Más información acerca de: ISymUnmanagedWriter::D método efineConstant'
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
ms.openlocfilehash: 4c3fd3986d42061272406150422f037236c4b9bf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762531"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="d6b0e-103">ISymUnmanagedWriter::DefineConstant (Método)</span><span class="sxs-lookup"><span data-stu-id="d6b0e-103">ISymUnmanagedWriter::DefineConstant Method</span></span>

<span data-ttu-id="d6b0e-104">Define un nombre para un valor constante.</span><span class="sxs-lookup"><span data-stu-id="d6b0e-104">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6b0e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6b0e-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6b0e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6b0e-106">Parameters</span></span>  

 `name`  
 <span data-ttu-id="d6b0e-107">de Puntero a `WCHAR` que define el nombre de la constante.</span><span class="sxs-lookup"><span data-stu-id="d6b0e-107">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="d6b0e-108">de Valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="d6b0e-108">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="d6b0e-109">[in] Tamaño de la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="d6b0e-109">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="d6b0e-110">de Firma de tipo de la constante.</span><span class="sxs-lookup"><span data-stu-id="d6b0e-110">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6b0e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d6b0e-111">Return Value</span></span>  

 <span data-ttu-id="d6b0e-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d6b0e-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6b0e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6b0e-113">Requirements</span></span>  

 <span data-ttu-id="d6b0e-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d6b0e-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b0e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6b0e-115">See also</span></span>

- [<span data-ttu-id="d6b0e-116">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6b0e-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="d6b0e-117">Método DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="d6b0e-117">DefineConstant2 Method</span></span>](isymunmanagedwriter2-defineconstant2-method.md)
