---
description: 'Más información acerca de: ISymUnmanagedWriter::D método efineLocalVariable'
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
ms.openlocfilehash: cd817e3002c2a55fd8bbd7e565283752926f746b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762375"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="f0be0-103">ISymUnmanagedWriter::DefineLocalVariable (Método)</span><span class="sxs-lookup"><span data-stu-id="f0be0-103">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>

<span data-ttu-id="f0be0-104">Define una única variable en el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="f0be0-104">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="f0be0-105">Se puede llamar a este método varias veces para una variable del mismo nombre que tiene varias casas en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="f0be0-105">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="f0be0-106">Sin embargo, en este caso, los valores de `startOffset` los `endOffset` parámetros y no deben superponerse.</span><span class="sxs-lookup"><span data-stu-id="f0be0-106">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0be0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0be0-107">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="f0be0-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f0be0-108">Parameters</span></span>  

 `name`  
 <span data-ttu-id="f0be0-109">de Puntero a `WCHAR` que define el nombre de la variable local.</span><span class="sxs-lookup"><span data-stu-id="f0be0-109">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="f0be0-110">de Atributos de la variable local.</span><span class="sxs-lookup"><span data-stu-id="f0be0-110">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="f0be0-111">de `ULONG32` Que indica el tamaño, en bytes, del `signature` búfer.</span><span class="sxs-lookup"><span data-stu-id="f0be0-111">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="f0be0-112">de Firma de la variable local.</span><span class="sxs-lookup"><span data-stu-id="f0be0-112">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="f0be0-113">de Tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="f0be0-113">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="f0be0-114">de Primera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="f0be0-114">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="f0be0-115">de Segunda dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="f0be0-115">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="f0be0-116">de Tercera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="f0be0-116">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="f0be0-117">de Desplazamiento inicial de la variable.</span><span class="sxs-lookup"><span data-stu-id="f0be0-117">[in] The start offset for the variable.</span></span> <span data-ttu-id="f0be0-118">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="f0be0-118">This parameter is optional.</span></span> <span data-ttu-id="f0be0-119">Si es 0, este parámetro se omite y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="f0be0-119">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="f0be0-120">Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="f0be0-120">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="f0be0-121">de Desplazamiento final de la variable.</span><span class="sxs-lookup"><span data-stu-id="f0be0-121">[in] The end offset for the variable.</span></span> <span data-ttu-id="f0be0-122">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="f0be0-122">This parameter is optional.</span></span> <span data-ttu-id="f0be0-123">Si es 0, este parámetro se omite y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="f0be0-123">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="f0be0-124">Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="f0be0-124">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0be0-125">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f0be0-125">Return Value</span></span>  

 <span data-ttu-id="f0be0-126">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f0be0-126">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0be0-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0be0-127">Requirements</span></span>  

 <span data-ttu-id="f0be0-128">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f0be0-128">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0be0-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0be0-129">See also</span></span>

- [<span data-ttu-id="f0be0-130">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f0be0-130">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="f0be0-131">Método DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="f0be0-131">DefineGlobalVariable Method</span></span>](isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="f0be0-132">Método DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="f0be0-132">DefineLocalVariable2 Method</span></span>](isymunmanagedwriter2-definelocalvariable2-method.md)
