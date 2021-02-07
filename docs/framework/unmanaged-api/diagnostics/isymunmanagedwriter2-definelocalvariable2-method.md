---
description: 'Más información acerca de: ISymUnmanagedWriter2::D efineLocalVariable2 (método)'
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
ms.openlocfilehash: 169a086b8420b5dbe20af8e16b21d5b41a958ead
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761816"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="f356b-103">ISymUnmanagedWriter2::DefineLocalVariable2 (Método)</span><span class="sxs-lookup"><span data-stu-id="f356b-103">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>

<span data-ttu-id="f356b-104">Define una única variable en el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="f356b-104">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="f356b-105">Se puede llamar a este método varias veces para una variable del mismo nombre que tiene varias casas en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="f356b-105">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="f356b-106">Sin embargo, en este caso, los valores de `startOffset` los `endOffset` parámetros y no deben superponerse.</span><span class="sxs-lookup"><span data-stu-id="f356b-106">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f356b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f356b-107">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="f356b-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f356b-108">Parameters</span></span>  

 `name`  
 <span data-ttu-id="f356b-109">de Nombre de la variable local.</span><span class="sxs-lookup"><span data-stu-id="f356b-109">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="f356b-110">de Atributos de la variable local.</span><span class="sxs-lookup"><span data-stu-id="f356b-110">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="f356b-111">de Símbolo (token) de metadatos de la firma.</span><span class="sxs-lookup"><span data-stu-id="f356b-111">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="f356b-112">de Tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="f356b-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="f356b-113">de Primera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="f356b-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="f356b-114">de Segunda dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="f356b-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="f356b-115">de Tercera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="f356b-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="f356b-116">de Desplazamiento inicial de la variable.</span><span class="sxs-lookup"><span data-stu-id="f356b-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="f356b-117">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="f356b-117">This parameter is optional.</span></span> <span data-ttu-id="f356b-118">Si es 0, este parámetro se omite y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="f356b-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="f356b-119">Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="f356b-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="f356b-120">de Desplazamiento final de la variable.</span><span class="sxs-lookup"><span data-stu-id="f356b-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="f356b-121">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="f356b-121">This parameter is optional.</span></span> <span data-ttu-id="f356b-122">Si es 0, este parámetro se omite y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="f356b-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="f356b-123">Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="f356b-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f356b-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f356b-124">Return Value</span></span>  

 <span data-ttu-id="f356b-125">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f356b-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f356b-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f356b-126">Requirements</span></span>  

 <span data-ttu-id="f356b-127">**Encabezado:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="f356b-127">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f356b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f356b-128">See also</span></span>

- [<span data-ttu-id="f356b-129">ISymUnmanagedWriter2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f356b-129">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="f356b-130">Método DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="f356b-130">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
