---
title: ISymUnmanagedWriter2::DefineLocalVariable2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2caa9b48fc92a1b2e82f574d37d99758e19382c7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133203"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="249ab-102">ISymUnmanagedWriter2::DefineLocalVariable2 (Método)</span><span class="sxs-lookup"><span data-stu-id="249ab-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="249ab-103">Define una única variable en el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="249ab-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="249ab-104">Este método puede llamarse varias veces para una variable del mismo nombre que tenga varias ubicaciones en un ámbito.</span><span class="sxs-lookup"><span data-stu-id="249ab-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="249ab-105">En este caso, sin embargo, los valores de la `startOffset` y `endOffset` parámetros no deben superponerse.</span><span class="sxs-lookup"><span data-stu-id="249ab-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="249ab-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="249ab-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="249ab-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="249ab-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="249ab-108">[in] El nombre de variable local.</span><span class="sxs-lookup"><span data-stu-id="249ab-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="249ab-109">[in] Atributos de la variable locales.</span><span class="sxs-lookup"><span data-stu-id="249ab-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="249ab-110">[in] El token de metadatos de la firma.</span><span class="sxs-lookup"><span data-stu-id="249ab-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="249ab-111">[in] El tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="249ab-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="249ab-112">[in] La primera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="249ab-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="249ab-113">[in] La segunda dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="249ab-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="249ab-114">[in] Tercera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="249ab-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="249ab-115">[in] El desplazamiento inicial de la variable.</span><span class="sxs-lookup"><span data-stu-id="249ab-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="249ab-116">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="249ab-116">This parameter is optional.</span></span> <span data-ttu-id="249ab-117">Si es 0, se omite este parámetro y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="249ab-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="249ab-118">Si es un valor distinto de cero, la variable está comprendida dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="249ab-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="249ab-119">[in] Desplazamiento final de la variable.</span><span class="sxs-lookup"><span data-stu-id="249ab-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="249ab-120">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="249ab-120">This parameter is optional.</span></span> <span data-ttu-id="249ab-121">Si es 0, se omite este parámetro y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="249ab-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="249ab-122">Si es un valor distinto de cero, la variable está comprendida dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="249ab-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="249ab-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="249ab-123">Return Value</span></span>  
 <span data-ttu-id="249ab-124">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="249ab-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="249ab-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="249ab-125">Requirements</span></span>  
 <span data-ttu-id="249ab-126">**Encabezado**: CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="249ab-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="249ab-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="249ab-127">See also</span></span>

- [<span data-ttu-id="249ab-128">ISymUnmanagedWriter2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="249ab-128">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="249ab-129">Método DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="249ab-129">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
