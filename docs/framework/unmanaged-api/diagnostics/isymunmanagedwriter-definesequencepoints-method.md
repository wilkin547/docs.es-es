---
description: 'Más información acerca de: ISymUnmanagedWriter::D método efineSequencePoints'
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
ms.openlocfilehash: 0c5ac9854ef341512f58cb1cd63ed7dfcde9962e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762336"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="a533d-103">ISymUnmanagedWriter::DefineSequencePoints (Método)</span><span class="sxs-lookup"><span data-stu-id="a533d-103">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>

<span data-ttu-id="a533d-104">Define un grupo de puntos de secuencia dentro del método actual.</span><span class="sxs-lookup"><span data-stu-id="a533d-104">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="a533d-105">Cada línea inicial y columna inicial definen el inicio de una instrucción dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="a533d-105">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="a533d-106">Cada línea final y columna final definen el final de una instrucción dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="a533d-106">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="a533d-107">Las matrices se deben ordenar en orden ascendente de desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="a533d-107">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="a533d-108">El desplazamiento siempre se mide desde el inicio del método, en bytes.</span><span class="sxs-lookup"><span data-stu-id="a533d-108">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a533d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a533d-109">Syntax</span></span>  
  
```cpp  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a533d-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a533d-110">Parameters</span></span>  

 `document`  
 <span data-ttu-id="a533d-111">de Objeto de documento para el que se definen los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="a533d-111">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="a533d-112">de `ULONG32` Que indica el tamaño de cada uno de los `offsets` `lines` búferes,, `columns` , `endLines` y `endColumns` .</span><span class="sxs-lookup"><span data-stu-id="a533d-112">[in] A `ULONG32` that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="a533d-113">de Desplazamiento de los puntos de secuencia medido desde el principio del método.</span><span class="sxs-lookup"><span data-stu-id="a533d-113">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="a533d-114">de Números de línea inicial de los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="a533d-114">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="a533d-115">de Números de columna inicial de los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="a533d-115">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="a533d-116">de Números de línea final de los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="a533d-116">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="a533d-117">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="a533d-117">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="a533d-118">de Números de columna final de los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="a533d-118">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="a533d-119">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="a533d-119">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a533d-120">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a533d-120">Return Value</span></span>  

 <span data-ttu-id="a533d-121">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a533d-121">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a533d-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a533d-122">Requirements</span></span>  

 <span data-ttu-id="a533d-123">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="a533d-123">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a533d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a533d-124">See also</span></span>

- [<span data-ttu-id="a533d-125">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a533d-125">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
