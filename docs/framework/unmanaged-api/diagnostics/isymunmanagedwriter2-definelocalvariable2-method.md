---
title: "ISymUnmanagedWriter2::DefineLocalVariable2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2.DefineLocalVariable2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1124b57bed16e349c753be872c1b709a287e6237
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="6170f-102">ISymUnmanagedWriter2::DefineLocalVariable2 (Método)</span><span class="sxs-lookup"><span data-stu-id="6170f-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="6170f-103">Define una única variable en el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="6170f-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="6170f-104">Este método puede llamarse varias veces para una variable del mismo nombre que tenga varias ubicaciones en un ámbito.</span><span class="sxs-lookup"><span data-stu-id="6170f-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="6170f-105">En este caso, sin embargo, los valores de la `startOffset` y `endOffset` no deben solaparse con parámetros.</span><span class="sxs-lookup"><span data-stu-id="6170f-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6170f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6170f-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6170f-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6170f-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6170f-108">[in] El nombre de variable local.</span><span class="sxs-lookup"><span data-stu-id="6170f-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="6170f-109">[in] Atributos de la variable locales.</span><span class="sxs-lookup"><span data-stu-id="6170f-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="6170f-110">[in] El token de metadatos de la firma.</span><span class="sxs-lookup"><span data-stu-id="6170f-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="6170f-111">[in] El tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="6170f-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="6170f-112">[in] La primera dirección para la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="6170f-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="6170f-113">[in] La segunda dirección para la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="6170f-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="6170f-114">[in] La tercera dirección de la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="6170f-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="6170f-115">[in] Desplazamiento inicial de la variable.</span><span class="sxs-lookup"><span data-stu-id="6170f-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="6170f-116">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="6170f-116">This parameter is optional.</span></span> <span data-ttu-id="6170f-117">Si es 0, se omite este parámetro y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="6170f-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="6170f-118">Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="6170f-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="6170f-119">[in] Desplazamiento final de la variable.</span><span class="sxs-lookup"><span data-stu-id="6170f-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="6170f-120">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="6170f-120">This parameter is optional.</span></span> <span data-ttu-id="6170f-121">Si es 0, se omite este parámetro y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="6170f-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="6170f-122">Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="6170f-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6170f-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6170f-123">Return Value</span></span>  
 <span data-ttu-id="6170f-124">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="6170f-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6170f-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6170f-125">Requirements</span></span>  
 <span data-ttu-id="6170f-126">**Encabezado:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="6170f-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6170f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6170f-127">See Also</span></span>  
 [<span data-ttu-id="6170f-128">ISymUnmanagedWriter2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6170f-128">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="6170f-129">DefineLocalVariable (método)</span><span class="sxs-lookup"><span data-stu-id="6170f-129">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
