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
ms.openlocfilehash: ac7559bd5431f45b266602404ddde9081aa2944d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614700"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="04ff2-102">ISymUnmanagedWriter2::DefineLocalVariable2 (Método)</span><span class="sxs-lookup"><span data-stu-id="04ff2-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="04ff2-103">Define una única variable en el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="04ff2-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="04ff2-104">Se puede llamar a este método varias veces para una variable del mismo nombre que tiene varias casas en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="04ff2-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="04ff2-105">Sin embargo, en este caso, los valores de `startOffset` los `endOffset` parámetros y no deben superponerse.</span><span class="sxs-lookup"><span data-stu-id="04ff2-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04ff2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04ff2-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="04ff2-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04ff2-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="04ff2-108">de Nombre de la variable local.</span><span class="sxs-lookup"><span data-stu-id="04ff2-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="04ff2-109">de Atributos de la variable local.</span><span class="sxs-lookup"><span data-stu-id="04ff2-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="04ff2-110">de Símbolo (token) de metadatos de la firma.</span><span class="sxs-lookup"><span data-stu-id="04ff2-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="04ff2-111">de Tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="04ff2-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="04ff2-112">de Primera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="04ff2-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="04ff2-113">de Segunda dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="04ff2-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="04ff2-114">de Tercera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="04ff2-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="04ff2-115">de Desplazamiento inicial de la variable.</span><span class="sxs-lookup"><span data-stu-id="04ff2-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="04ff2-116">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="04ff2-116">This parameter is optional.</span></span> <span data-ttu-id="04ff2-117">Si es 0, este parámetro se omite y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="04ff2-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="04ff2-118">Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="04ff2-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="04ff2-119">de Desplazamiento final de la variable.</span><span class="sxs-lookup"><span data-stu-id="04ff2-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="04ff2-120">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="04ff2-120">This parameter is optional.</span></span> <span data-ttu-id="04ff2-121">Si es 0, este parámetro se omite y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="04ff2-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="04ff2-122">Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="04ff2-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04ff2-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="04ff2-123">Return Value</span></span>  
 <span data-ttu-id="04ff2-124">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="04ff2-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04ff2-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04ff2-125">Requirements</span></span>  
 <span data-ttu-id="04ff2-126">**Encabezado:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="04ff2-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04ff2-127">Consulta también</span><span class="sxs-lookup"><span data-stu-id="04ff2-127">See also</span></span>

- [<span data-ttu-id="04ff2-128">ISymUnmanagedWriter2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04ff2-128">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="04ff2-129">Método DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="04ff2-129">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
