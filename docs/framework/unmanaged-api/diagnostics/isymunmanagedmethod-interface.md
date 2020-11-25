---
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
ms.openlocfilehash: b72a77fecd15a43efbddd9dfd4618897c3372f88
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699279"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="87682-102">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87682-102">ISymUnmanagedMethod Interface</span></span>

<span data-ttu-id="87682-103">Representa un método dentro del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="87682-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="87682-104">Esta interfaz proporciona acceso únicamente a los atributos relacionados con símbolos de un método, en lugar de los atributos relacionados con el tipo.</span><span class="sxs-lookup"><span data-stu-id="87682-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87682-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="87682-105">Methods</span></span>  
  
|<span data-ttu-id="87682-106">Método</span><span class="sxs-lookup"><span data-stu-id="87682-106">Method</span></span>|<span data-ttu-id="87682-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="87682-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87682-108">Método GetNamespace</span><span class="sxs-lookup"><span data-stu-id="87682-108">GetNamespace Method</span></span>](isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="87682-109">Obtiene el espacio de nombres en el que se define este método.</span><span class="sxs-lookup"><span data-stu-id="87682-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="87682-110">GetOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="87682-110">GetOffset Method</span></span>](isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="87682-111">Devuelve el desplazamiento dentro de este método que corresponde a una posición determinada dentro de un documento.</span><span class="sxs-lookup"><span data-stu-id="87682-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="87682-112">Método GetParameters</span><span class="sxs-lookup"><span data-stu-id="87682-112">GetParameters Method</span></span>](isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="87682-113">Obtiene los parámetros de este método.</span><span class="sxs-lookup"><span data-stu-id="87682-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="87682-114">Método GetRanges</span><span class="sxs-lookup"><span data-stu-id="87682-114">GetRanges Method</span></span>](isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="87682-115">Dada una posición en un documento, devuelve una matriz de pares de desplazamiento inicial y final que corresponden a los intervalos del lenguaje intermedio de Microsoft (MSIL) que cubre la posición dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="87682-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="87682-116">Método GetRootScope</span><span class="sxs-lookup"><span data-stu-id="87682-116">GetRootScope Method</span></span>](isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="87682-117">Obtiene el ámbito léxico raíz dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="87682-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="87682-118">Este ámbito abarca el método completo.</span><span class="sxs-lookup"><span data-stu-id="87682-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="87682-119">Método GetScopeFromOffset</span><span class="sxs-lookup"><span data-stu-id="87682-119">GetScopeFromOffset Method</span></span>](isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="87682-120">Obtiene el ámbito léxico más envolvente dentro de este método que incluye el desplazamiento determinado.</span><span class="sxs-lookup"><span data-stu-id="87682-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="87682-121">Método GetSequencePointCount</span><span class="sxs-lookup"><span data-stu-id="87682-121">GetSequencePointCount Method</span></span>](isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="87682-122">Obtiene el recuento de puntos de secuencia dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="87682-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="87682-123">Método GetSequencePoints</span><span class="sxs-lookup"><span data-stu-id="87682-123">GetSequencePoints Method</span></span>](isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="87682-124">Obtiene todos los puntos de secuencia de este método.</span><span class="sxs-lookup"><span data-stu-id="87682-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="87682-125">Método GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="87682-125">GetSourceStartEnd Method</span></span>](isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="87682-126">Obtiene las posiciones de documento inicial y final para el origen de este método.</span><span class="sxs-lookup"><span data-stu-id="87682-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="87682-127">GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="87682-127">GetToken Method</span></span>](isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="87682-128">Devuelve el símbolo (token) de metadatos para este método.</span><span class="sxs-lookup"><span data-stu-id="87682-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87682-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87682-129">Requirements</span></span>  

 <span data-ttu-id="87682-130">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="87682-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87682-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87682-131">See also</span></span>

- [<span data-ttu-id="87682-132">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="87682-132">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
