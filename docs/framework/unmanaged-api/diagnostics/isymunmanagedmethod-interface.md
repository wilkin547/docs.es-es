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
ms.openlocfilehash: c29656a4787c674886505a3be2508470460dfc10
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136531"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="e7bbc-102">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7bbc-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="e7bbc-103">Representa un método en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e7bbc-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="e7bbc-104">Esta interfaz proporciona acceso a solo los atributos relacionados con el símbolo de un método, en lugar de los atributos relacionados con el tipo.</span><span class="sxs-lookup"><span data-stu-id="e7bbc-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7bbc-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e7bbc-105">Methods</span></span>  
  
|<span data-ttu-id="e7bbc-106">Método</span><span class="sxs-lookup"><span data-stu-id="e7bbc-106">Method</span></span>|<span data-ttu-id="e7bbc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7bbc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e7bbc-108">Método GetNamespace</span><span class="sxs-lookup"><span data-stu-id="e7bbc-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="e7bbc-109">Obtiene el espacio de nombres dentro del cual se define este método.</span><span class="sxs-lookup"><span data-stu-id="e7bbc-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="e7bbc-110">Método GetOffset</span><span class="sxs-lookup"><span data-stu-id="e7bbc-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="e7bbc-111">Devuelve el desplazamiento dentro de este método que corresponde a una posición dada dentro de un documento.</span><span class="sxs-lookup"><span data-stu-id="e7bbc-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="e7bbc-112">Método GetParameters</span><span class="sxs-lookup"><span data-stu-id="e7bbc-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="e7bbc-113">Obtiene los parámetros de este método.</span><span class="sxs-lookup"><span data-stu-id="e7bbc-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="e7bbc-114">Método GetRanges</span><span class="sxs-lookup"><span data-stu-id="e7bbc-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="e7bbc-115">Dada una posición en un documento, devuelve una matriz de pares de desplazamiento inicial y final que corresponden a los intervalos de lenguaje intermedio de Microsoft (MSIL) que cubre la posición dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="e7bbc-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="e7bbc-116">Método GetRootScope</span><span class="sxs-lookup"><span data-stu-id="e7bbc-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="e7bbc-117">Obtiene el ámbito léxico raíz dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="e7bbc-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="e7bbc-118">Este ámbito abarca el método completo.</span><span class="sxs-lookup"><span data-stu-id="e7bbc-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="e7bbc-119">Método GetScopeFromOffset</span><span class="sxs-lookup"><span data-stu-id="e7bbc-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="e7bbc-120">Obtiene el ámbito léxico más envolvente dentro de este método que contiene el desplazamiento especificado.</span><span class="sxs-lookup"><span data-stu-id="e7bbc-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="e7bbc-121">Método GetSequencePointCount</span><span class="sxs-lookup"><span data-stu-id="e7bbc-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="e7bbc-122">Obtiene el recuento de puntos de secuencia dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="e7bbc-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="e7bbc-123">Método GetSequencePoints</span><span class="sxs-lookup"><span data-stu-id="e7bbc-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="e7bbc-124">Obtiene todos los puntos de secuencia dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="e7bbc-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="e7bbc-125">Método GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="e7bbc-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="e7bbc-126">Obtiene las posiciones de documento de inicio y finalización para el origen de este método.</span><span class="sxs-lookup"><span data-stu-id="e7bbc-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="e7bbc-127">Método GetToken</span><span class="sxs-lookup"><span data-stu-id="e7bbc-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="e7bbc-128">Devuelve el token de metadatos para este método.</span><span class="sxs-lookup"><span data-stu-id="e7bbc-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e7bbc-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7bbc-129">Requirements</span></span>  
 <span data-ttu-id="e7bbc-130">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e7bbc-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7bbc-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7bbc-131">See also</span></span>

- [<span data-ttu-id="e7bbc-132">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="e7bbc-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
