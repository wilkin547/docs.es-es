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
ms.openlocfilehash: 1d3ccb2265f056d5776199d997dc067c8d5513e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448786"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="98714-102">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="98714-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="98714-103">Representa un método dentro del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="98714-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="98714-104">Esta interfaz proporciona acceso únicamente a los atributos relacionados con símbolos de un método, en lugar de los atributos relacionados con el tipo.</span><span class="sxs-lookup"><span data-stu-id="98714-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98714-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="98714-105">Methods</span></span>  
  
|<span data-ttu-id="98714-106">Método</span><span class="sxs-lookup"><span data-stu-id="98714-106">Method</span></span>|<span data-ttu-id="98714-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="98714-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98714-108">GetNamespace (método)</span><span class="sxs-lookup"><span data-stu-id="98714-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="98714-109">Obtiene el espacio de nombres en el que se define este método.</span><span class="sxs-lookup"><span data-stu-id="98714-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="98714-110">GetOffset (método)</span><span class="sxs-lookup"><span data-stu-id="98714-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="98714-111">Devuelve el desplazamiento dentro de este método que corresponde a una posición determinada dentro de un documento.</span><span class="sxs-lookup"><span data-stu-id="98714-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="98714-112">GetParameters (método)</span><span class="sxs-lookup"><span data-stu-id="98714-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="98714-113">Obtiene los parámetros de este método.</span><span class="sxs-lookup"><span data-stu-id="98714-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="98714-114">GetRanges (método)</span><span class="sxs-lookup"><span data-stu-id="98714-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="98714-115">Dada una posición en un documento, devuelve una matriz de pares de desplazamiento inicial y final que corresponden a los intervalos del lenguaje intermedio de Microsoft (MSIL) que cubre la posición dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="98714-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="98714-116">GetRootScope (método)</span><span class="sxs-lookup"><span data-stu-id="98714-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="98714-117">Obtiene el ámbito léxico raíz dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="98714-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="98714-118">Este ámbito abarca el método completo.</span><span class="sxs-lookup"><span data-stu-id="98714-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="98714-119">GetScopeFromOffset (método)</span><span class="sxs-lookup"><span data-stu-id="98714-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="98714-120">Obtiene el ámbito léxico más envolvente dentro de este método que incluye el desplazamiento determinado.</span><span class="sxs-lookup"><span data-stu-id="98714-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="98714-121">GetSequencePointCount (método)</span><span class="sxs-lookup"><span data-stu-id="98714-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="98714-122">Obtiene el recuento de puntos de secuencia dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="98714-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="98714-123">GetSequencePoints (método)</span><span class="sxs-lookup"><span data-stu-id="98714-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="98714-124">Obtiene todos los puntos de secuencia de este método.</span><span class="sxs-lookup"><span data-stu-id="98714-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="98714-125">GetSourceStartEnd (método)</span><span class="sxs-lookup"><span data-stu-id="98714-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="98714-126">Obtiene las posiciones de documento inicial y final para el origen de este método.</span><span class="sxs-lookup"><span data-stu-id="98714-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="98714-127">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="98714-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="98714-128">Devuelve el símbolo (token) de metadatos de este método.</span><span class="sxs-lookup"><span data-stu-id="98714-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98714-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98714-129">Requirements</span></span>  
 <span data-ttu-id="98714-130">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="98714-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98714-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="98714-131">See also</span></span>

- [<span data-ttu-id="98714-132">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="98714-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
