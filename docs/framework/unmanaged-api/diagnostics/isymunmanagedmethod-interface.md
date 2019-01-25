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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b19e5ce88ea34188b2757d2a0c313341fbf1e7e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604267"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="ee239-102">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee239-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="ee239-103">Representa un método en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="ee239-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="ee239-104">Esta interfaz proporciona acceso a solo los atributos relacionados con el símbolo de un método, en lugar de los atributos relacionados con el tipo.</span><span class="sxs-lookup"><span data-stu-id="ee239-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee239-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ee239-105">Methods</span></span>  
  
|<span data-ttu-id="ee239-106">Método</span><span class="sxs-lookup"><span data-stu-id="ee239-106">Method</span></span>|<span data-ttu-id="ee239-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee239-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee239-108">GetNamespace (método)</span><span class="sxs-lookup"><span data-stu-id="ee239-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="ee239-109">Obtiene el espacio de nombres dentro del cual se define este método.</span><span class="sxs-lookup"><span data-stu-id="ee239-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="ee239-110">GetOffset (método)</span><span class="sxs-lookup"><span data-stu-id="ee239-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="ee239-111">Devuelve el desplazamiento dentro de este método que corresponde a una posición dada dentro de un documento.</span><span class="sxs-lookup"><span data-stu-id="ee239-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="ee239-112">GetParameters (método)</span><span class="sxs-lookup"><span data-stu-id="ee239-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="ee239-113">Obtiene los parámetros de este método.</span><span class="sxs-lookup"><span data-stu-id="ee239-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="ee239-114">GetRanges (método)</span><span class="sxs-lookup"><span data-stu-id="ee239-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="ee239-115">Dada una posición en un documento, devuelve una matriz de pares de desplazamiento inicial y final que corresponden a los intervalos de lenguaje intermedio de Microsoft (MSIL) que cubre la posición dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="ee239-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="ee239-116">GetRootScope (método)</span><span class="sxs-lookup"><span data-stu-id="ee239-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="ee239-117">Obtiene el ámbito léxico raíz dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="ee239-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="ee239-118">Este ámbito abarca el método completo.</span><span class="sxs-lookup"><span data-stu-id="ee239-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="ee239-119">GetScopeFromOffset (método)</span><span class="sxs-lookup"><span data-stu-id="ee239-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="ee239-120">Obtiene el ámbito léxico más envolvente dentro de este método que contiene el desplazamiento especificado.</span><span class="sxs-lookup"><span data-stu-id="ee239-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="ee239-121">GetSequencePointCount (método)</span><span class="sxs-lookup"><span data-stu-id="ee239-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="ee239-122">Obtiene el recuento de puntos de secuencia dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="ee239-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="ee239-123">GetSequencePoints (método)</span><span class="sxs-lookup"><span data-stu-id="ee239-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="ee239-124">Obtiene todos los puntos de secuencia dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="ee239-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="ee239-125">GetSourceStartEnd (método)</span><span class="sxs-lookup"><span data-stu-id="ee239-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="ee239-126">Obtiene las posiciones de documento de inicio y finalización para el origen de este método.</span><span class="sxs-lookup"><span data-stu-id="ee239-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="ee239-127">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="ee239-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="ee239-128">Devuelve el token de metadatos para este método.</span><span class="sxs-lookup"><span data-stu-id="ee239-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee239-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee239-129">Requirements</span></span>  
 <span data-ttu-id="ee239-130">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ee239-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee239-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee239-131">See also</span></span>
- [<span data-ttu-id="ee239-132">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="ee239-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
