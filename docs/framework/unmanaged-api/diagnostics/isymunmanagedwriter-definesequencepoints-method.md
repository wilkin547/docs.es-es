---
title: ISymUnmanagedWriter::DefineSequencePoints (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 735b33ac1f049f8d4d3740239e7c34a6fa16dd32
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146944"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="5f13c-102">ISymUnmanagedWriter::DefineSequencePoints (Método)</span><span class="sxs-lookup"><span data-stu-id="5f13c-102">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>
<span data-ttu-id="5f13c-103">Define un grupo de puntos de secuencia dentro del método actual.</span><span class="sxs-lookup"><span data-stu-id="5f13c-103">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="5f13c-104">Cada línea de inicio y la columna inicial define el principio de una instrucción dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="5f13c-104">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="5f13c-105">Cada línea final y columna final definen el final de una instrucción dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="5f13c-105">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="5f13c-106">Las matrices se deben ordenar en orden creciente de los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="5f13c-106">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="5f13c-107">El desplazamiento siempre se mide desde el principio del método, en bytes.</span><span class="sxs-lookup"><span data-stu-id="5f13c-107">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f13c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f13c-108">Syntax</span></span>  
  
```  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f13c-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f13c-109">Parameters</span></span>  
 `document`  
 <span data-ttu-id="5f13c-110">[in] El objeto de documento para el que se definen los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="5f13c-110">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="5f13c-111">[in] Un `ULONG32` que indica el tamaño de cada uno de los `offsets`, `lines`, `columns`, `endLines`, y `endColumns` búferes.</span><span class="sxs-lookup"><span data-stu-id="5f13c-111">[in] A `ULONG32` that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="5f13c-112">[in] El desplazamiento de los puntos de secuencia medido desde el principio del método.</span><span class="sxs-lookup"><span data-stu-id="5f13c-112">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="5f13c-113">[in] Los números de línea inicial de los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="5f13c-113">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="5f13c-114">[in] Los números de columna a partir de los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="5f13c-114">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="5f13c-115">[in] Los números de línea final de los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="5f13c-115">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="5f13c-116">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="5f13c-116">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="5f13c-117">[in] Los números de columna final de los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="5f13c-117">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="5f13c-118">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="5f13c-118">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f13c-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5f13c-119">Return Value</span></span>  
 <span data-ttu-id="5f13c-120">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="5f13c-120">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f13c-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f13c-121">Requirements</span></span>  
 <span data-ttu-id="5f13c-122">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5f13c-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f13c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f13c-123">See also</span></span>

- [<span data-ttu-id="5f13c-124">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f13c-124">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
