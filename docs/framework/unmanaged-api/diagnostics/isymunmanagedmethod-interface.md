---
description: 'Más información acerca de: interfaz ISymUnmanagedMethod'
title: ISymUnmanagedMethod (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
ms.openlocfilehash: 18f87784a959ddc62415592e51d1971ea10f90bf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709963"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="30725-103">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30725-103">ISymUnmanagedMethod Interface</span></span>

<span data-ttu-id="30725-104">Representa un método dentro del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="30725-104">Represents a method within the symbol store.</span></span> <span data-ttu-id="30725-105">Esta interfaz proporciona acceso únicamente a los atributos relacionados con símbolos de un método, en lugar de los atributos relacionados con el tipo.</span><span class="sxs-lookup"><span data-stu-id="30725-105">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="30725-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="30725-106">Methods</span></span>  
  
|<span data-ttu-id="30725-107">Método</span><span class="sxs-lookup"><span data-stu-id="30725-107">Method</span></span>|<span data-ttu-id="30725-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="30725-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="30725-109">Método GetNamespace</span><span class="sxs-lookup"><span data-stu-id="30725-109">GetNamespace Method</span></span>](isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="30725-110">Obtiene el espacio de nombres en el que se define este método.</span><span class="sxs-lookup"><span data-stu-id="30725-110">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="30725-111">Método GetOffset</span><span class="sxs-lookup"><span data-stu-id="30725-111">GetOffset Method</span></span>](isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="30725-112">Devuelve el desplazamiento dentro de este método que corresponde a una posición determinada dentro de un documento.</span><span class="sxs-lookup"><span data-stu-id="30725-112">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="30725-113">Método GetParameters</span><span class="sxs-lookup"><span data-stu-id="30725-113">GetParameters Method</span></span>](isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="30725-114">Obtiene los parámetros de este método.</span><span class="sxs-lookup"><span data-stu-id="30725-114">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="30725-115">Método GetRanges</span><span class="sxs-lookup"><span data-stu-id="30725-115">GetRanges Method</span></span>](isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="30725-116">Dada una posición en un documento, devuelve una matriz de pares de desplazamiento inicial y final que corresponden a los intervalos del lenguaje intermedio de Microsoft (MSIL) que cubre la posición dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="30725-116">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="30725-117">Método GetRootScope</span><span class="sxs-lookup"><span data-stu-id="30725-117">GetRootScope Method</span></span>](isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="30725-118">Obtiene el ámbito léxico raíz dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="30725-118">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="30725-119">Este ámbito abarca el método completo.</span><span class="sxs-lookup"><span data-stu-id="30725-119">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="30725-120">Método GetScopeFromOffset</span><span class="sxs-lookup"><span data-stu-id="30725-120">GetScopeFromOffset Method</span></span>](isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="30725-121">Obtiene el ámbito léxico más envolvente dentro de este método que incluye el desplazamiento determinado.</span><span class="sxs-lookup"><span data-stu-id="30725-121">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="30725-122">Método GetSequencePointCount</span><span class="sxs-lookup"><span data-stu-id="30725-122">GetSequencePointCount Method</span></span>](isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="30725-123">Obtiene el recuento de puntos de secuencia dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="30725-123">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="30725-124">Método GetSequencePoints</span><span class="sxs-lookup"><span data-stu-id="30725-124">GetSequencePoints Method</span></span>](isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="30725-125">Obtiene todos los puntos de secuencia de este método.</span><span class="sxs-lookup"><span data-stu-id="30725-125">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="30725-126">Método GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="30725-126">GetSourceStartEnd Method</span></span>](isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="30725-127">Obtiene las posiciones de documento inicial y final para el origen de este método.</span><span class="sxs-lookup"><span data-stu-id="30725-127">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="30725-128">GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="30725-128">GetToken Method</span></span>](isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="30725-129">Devuelve el símbolo (token) de metadatos para este método.</span><span class="sxs-lookup"><span data-stu-id="30725-129">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="30725-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30725-130">Requirements</span></span>  

 <span data-ttu-id="30725-131">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="30725-131">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30725-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="30725-132">See also</span></span>

- [<span data-ttu-id="30725-133">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="30725-133">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
