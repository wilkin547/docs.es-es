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
ms.openlocfilehash: 5730cdd910257d762230f5e54576d5e0a7ac1adb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614830"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="5beee-102">ISymUnmanagedWriter::DefineLocalVariable (Método)</span><span class="sxs-lookup"><span data-stu-id="5beee-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="5beee-103">Define una única variable en el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="5beee-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="5beee-104">Se puede llamar a este método varias veces para una variable del mismo nombre que tiene varias casas en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="5beee-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="5beee-105">Sin embargo, en este caso, los valores de `startOffset` los `endOffset` parámetros y no deben superponerse.</span><span class="sxs-lookup"><span data-stu-id="5beee-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5beee-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5beee-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5beee-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5beee-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="5beee-108">de Puntero a `WCHAR` que define el nombre de la variable local.</span><span class="sxs-lookup"><span data-stu-id="5beee-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="5beee-109">de Atributos de la variable local.</span><span class="sxs-lookup"><span data-stu-id="5beee-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="5beee-110">de `ULONG32`Que indica el tamaño, en bytes, del `signature` búfer.</span><span class="sxs-lookup"><span data-stu-id="5beee-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="5beee-111">de Firma de la variable local.</span><span class="sxs-lookup"><span data-stu-id="5beee-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="5beee-112">de Tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="5beee-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="5beee-113">de Primera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="5beee-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="5beee-114">de Segunda dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="5beee-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="5beee-115">de Tercera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="5beee-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="5beee-116">de Desplazamiento inicial de la variable.</span><span class="sxs-lookup"><span data-stu-id="5beee-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="5beee-117">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="5beee-117">This parameter is optional.</span></span> <span data-ttu-id="5beee-118">Si es 0, este parámetro se omite y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="5beee-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="5beee-119">Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="5beee-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="5beee-120">de Desplazamiento final de la variable.</span><span class="sxs-lookup"><span data-stu-id="5beee-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="5beee-121">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="5beee-121">This parameter is optional.</span></span> <span data-ttu-id="5beee-122">Si es 0, este parámetro se omite y la variable se define en todo el ámbito.</span><span class="sxs-lookup"><span data-stu-id="5beee-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="5beee-123">Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="5beee-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5beee-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5beee-124">Return Value</span></span>  
 <span data-ttu-id="5beee-125">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="5beee-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5beee-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5beee-126">Requirements</span></span>  
 <span data-ttu-id="5beee-127">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5beee-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5beee-128">Consulta también</span><span class="sxs-lookup"><span data-stu-id="5beee-128">See also</span></span>

- [<span data-ttu-id="5beee-129">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5beee-129">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="5beee-130">Método DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="5beee-130">DefineGlobalVariable Method</span></span>](isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="5beee-131">Método DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="5beee-131">DefineLocalVariable2 Method</span></span>](isymunmanagedwriter2-definelocalvariable2-method.md)
