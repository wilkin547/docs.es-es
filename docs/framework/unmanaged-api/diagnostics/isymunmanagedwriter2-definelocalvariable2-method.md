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
ms.openlocfilehash: 595cc3d8c503a5a6b2cbcb6665f7ff8aff5044d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="ae761-102">ISymUnmanagedWriter2::DefineLocalVariable2 (Método)</span><span class="sxs-lookup"><span data-stu-id="ae761-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="ae761-103">Define una única variable en el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="ae761-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="ae761-104">Este método puede llamarse varias veces para una variable del mismo nombre que tenga varias ubicaciones en un ámbito.</span><span class="sxs-lookup"><span data-stu-id="ae761-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="ae761-105">En este caso, sin embargo, los valores de la `startOffset` y `endOffset` no deben solaparse con parámetros.</span><span class="sxs-lookup"><span data-stu-id="ae761-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae761-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae761-106">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="ae761-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae761-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="ae761-108">[in] El nombre de variable local.</span><span class="sxs-lookup"><span data-stu-id="ae761-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="ae761-109">[in] Atributos de la variable locales.</span><span class="sxs-lookup"><span data-stu-id="ae761-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="ae761-110">[in] El token de metadatos de la firma.</span><span class="sxs-lookup"><span data-stu-id="ae761-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="ae761-111">[in] El tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="ae761-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="ae761-112">[in] La primera dirección para la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="ae761-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="ae761-113">[in] La segunda dirección para la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="ae761-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="ae761-114">[in] La tercera dirección de la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="ae761-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="ae761-115">[in] Desplazamiento inicial de la variable.</span><span class="sxs-lookup"><span data-stu-id="ae761-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="ae761-116">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="ae761-116">This parameter is optional.</span></span> <span data-ttu-id="ae761-117">Si es 0, se omite este parámetro y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="ae761-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="ae761-118">Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="ae761-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="ae761-119">[in] Desplazamiento final de la variable.</span><span class="sxs-lookup"><span data-stu-id="ae761-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="ae761-120">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="ae761-120">This parameter is optional.</span></span> <span data-ttu-id="ae761-121">Si es 0, se omite este parámetro y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="ae761-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="ae761-122">Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="ae761-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae761-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ae761-123">Return Value</span></span>  
 <span data-ttu-id="ae761-124">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="ae761-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae761-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae761-125">Requirements</span></span>  
 <span data-ttu-id="ae761-126">**Encabezado:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="ae761-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae761-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae761-127">See Also</span></span>  
 [<span data-ttu-id="ae761-128">ISymUnmanagedWriter2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae761-128">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="ae761-129">DefineLocalVariable (método)</span><span class="sxs-lookup"><span data-stu-id="ae761-129">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
