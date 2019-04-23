---
title: ISymUnmanagedWriter::DefineLocalVariable (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c561eb70f0e3d243984decfb39629601f8eeea37
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125306"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="0f5d0-102">ISymUnmanagedWriter::DefineLocalVariable (Método)</span><span class="sxs-lookup"><span data-stu-id="0f5d0-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="0f5d0-103">Define una única variable en el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="0f5d0-104">Este método puede llamarse varias veces para una variable del mismo nombre que tenga varias ubicaciones en un ámbito.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="0f5d0-105">En este caso, sin embargo, los valores de la `startOffset` y `endOffset` parámetros no deben superponerse.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f5d0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f5d0-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f5d0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f5d0-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="0f5d0-108">[in] Un puntero a un `WCHAR` que define el nombre de variable local.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="0f5d0-109">[in] Atributos de la variable locales.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="0f5d0-110">[in] Un `ULONG32` que indica el tamaño, en bytes, de la `signature` búfer.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="0f5d0-111">[in] La firma de variable local.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="0f5d0-112">[in] El tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="0f5d0-113">[in] La primera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="0f5d0-114">[in] La segunda dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="0f5d0-115">[in] Tercera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="0f5d0-116">[in] El desplazamiento inicial de la variable.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="0f5d0-117">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-117">This parameter is optional.</span></span> <span data-ttu-id="0f5d0-118">Si es 0, se omite este parámetro y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="0f5d0-119">Si es un valor distinto de cero, la variable está comprendida dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="0f5d0-120">[in] Desplazamiento final de la variable.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="0f5d0-121">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-121">This parameter is optional.</span></span> <span data-ttu-id="0f5d0-122">Si es 0, se omite este parámetro y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="0f5d0-123">Si es un valor distinto de cero, la variable está comprendida dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f5d0-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0f5d0-124">Return Value</span></span>  
 <span data-ttu-id="0f5d0-125">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f5d0-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f5d0-126">Requirements</span></span>  
 <span data-ttu-id="0f5d0-127">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0f5d0-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f5d0-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f5d0-128">See also</span></span>

- [<span data-ttu-id="0f5d0-129">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f5d0-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="0f5d0-130">DefineGlobalVariable (método)</span><span class="sxs-lookup"><span data-stu-id="0f5d0-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="0f5d0-131">DefineLocalVariable2 (método)</span><span class="sxs-lookup"><span data-stu-id="0f5d0-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
