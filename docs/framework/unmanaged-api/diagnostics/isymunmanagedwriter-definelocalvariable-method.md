---
title: "ISymUnmanagedWriter::DefineLocalVariable (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineLocalVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89ea3e23166b4745b34b7c2af498d29564cdd68d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="80f9b-102">ISymUnmanagedWriter::DefineLocalVariable (Método)</span><span class="sxs-lookup"><span data-stu-id="80f9b-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="80f9b-103">Define una única variable en el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="80f9b-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="80f9b-104">Este método puede llamarse varias veces para una variable del mismo nombre que tenga varias ubicaciones en un ámbito.</span><span class="sxs-lookup"><span data-stu-id="80f9b-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="80f9b-105">En este caso, sin embargo, los valores de la `startOffset` y `endOffset` no deben solaparse con parámetros.</span><span class="sxs-lookup"><span data-stu-id="80f9b-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80f9b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80f9b-106">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="80f9b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80f9b-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="80f9b-108">[in] Un puntero a un `WCHAR` que define el nombre de variable local.</span><span class="sxs-lookup"><span data-stu-id="80f9b-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="80f9b-109">[in] Atributos de la variable locales.</span><span class="sxs-lookup"><span data-stu-id="80f9b-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="80f9b-110">[in] A `ULONG32` que indica el tamaño, en bytes, de la `signature` búfer.</span><span class="sxs-lookup"><span data-stu-id="80f9b-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="80f9b-111">[in] La firma de variable local.</span><span class="sxs-lookup"><span data-stu-id="80f9b-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="80f9b-112">[in] El tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="80f9b-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="80f9b-113">[in] La primera dirección para la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="80f9b-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="80f9b-114">[in] La segunda dirección para la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="80f9b-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="80f9b-115">[in] La tercera dirección de la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="80f9b-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="80f9b-116">[in] Desplazamiento inicial de la variable.</span><span class="sxs-lookup"><span data-stu-id="80f9b-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="80f9b-117">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="80f9b-117">This parameter is optional.</span></span> <span data-ttu-id="80f9b-118">Si es 0, se omite este parámetro y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="80f9b-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="80f9b-119">Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="80f9b-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="80f9b-120">[in] Desplazamiento final de la variable.</span><span class="sxs-lookup"><span data-stu-id="80f9b-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="80f9b-121">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="80f9b-121">This parameter is optional.</span></span> <span data-ttu-id="80f9b-122">Si es 0, se omite este parámetro y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="80f9b-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="80f9b-123">Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="80f9b-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80f9b-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="80f9b-124">Return Value</span></span>  
 <span data-ttu-id="80f9b-125">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="80f9b-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80f9b-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80f9b-126">Requirements</span></span>  
 <span data-ttu-id="80f9b-127">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="80f9b-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f9b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="80f9b-128">See Also</span></span>  
 [<span data-ttu-id="80f9b-129">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="80f9b-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="80f9b-130">DefineGlobalVariable (método)</span><span class="sxs-lookup"><span data-stu-id="80f9b-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)  
 [<span data-ttu-id="80f9b-131">DefineLocalVariable2 (método)</span><span class="sxs-lookup"><span data-stu-id="80f9b-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
