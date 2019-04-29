---
title: ISymUnmanagedDocument (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33213aced635549dd439cf679d89367a71baa7c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939781"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="e1eb7-102">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1eb7-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="e1eb7-103">Representa un documento al que hace referencia un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e1eb7-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="e1eb7-104">Un documento se define mediante un localizador uniforme de recursos (URL) y un GUID de tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="e1eb7-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="e1eb7-105">Puede buscar el documento, independientemente de cómo se almacenan utilizando la dirección URL y GUID del tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="e1eb7-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="e1eb7-106">Puede almacenar el código fuente del documento en el almacén de símbolos y recuperarlo a través de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="e1eb7-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1eb7-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="e1eb7-107">Methods</span></span>  
  
|<span data-ttu-id="e1eb7-108">Método</span><span class="sxs-lookup"><span data-stu-id="e1eb7-108">Method</span></span>|<span data-ttu-id="e1eb7-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1eb7-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1eb7-110">FindClosestLine (método)</span><span class="sxs-lookup"><span data-stu-id="e1eb7-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="e1eb7-111">Devuelve la línea más próxima que sea un punto de secuencia, se especifica una línea en este documento que puede o no ser un punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="e1eb7-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="e1eb7-112">GetCheckSum (método)</span><span class="sxs-lookup"><span data-stu-id="e1eb7-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="e1eb7-113">Obtiene la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="e1eb7-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="e1eb7-114">GetCheckSumAlgorithmId (método)</span><span class="sxs-lookup"><span data-stu-id="e1eb7-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="e1eb7-115">Obtiene el identificador del algoritmo de suma de comprobación o devuelve un GUID de todos los ceros si no hay ninguna suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="e1eb7-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="e1eb7-116">GetDocumentType (método)</span><span class="sxs-lookup"><span data-stu-id="e1eb7-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="e1eb7-117">Obtiene el tipo de documento de este documento.</span><span class="sxs-lookup"><span data-stu-id="e1eb7-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="e1eb7-118">GetLanguage (método)</span><span class="sxs-lookup"><span data-stu-id="e1eb7-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="e1eb7-119">Obtiene el identificador de idioma de este documento.</span><span class="sxs-lookup"><span data-stu-id="e1eb7-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="e1eb7-120">GetLanguageVendor (método)</span><span class="sxs-lookup"><span data-stu-id="e1eb7-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="e1eb7-121">Obtiene el proveedor de lenguaje de este documento.</span><span class="sxs-lookup"><span data-stu-id="e1eb7-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="e1eb7-122">GetSourceLength (método)</span><span class="sxs-lookup"><span data-stu-id="e1eb7-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="e1eb7-123">Obtiene la longitud, en bytes, del código fuente incrustado.</span><span class="sxs-lookup"><span data-stu-id="e1eb7-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="e1eb7-124">GetSourceRange (método)</span><span class="sxs-lookup"><span data-stu-id="e1eb7-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="e1eb7-125">Devuelve el intervalo especificado de código fuente incrustado en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="e1eb7-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="e1eb7-126">GetURL (método)</span><span class="sxs-lookup"><span data-stu-id="e1eb7-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="e1eb7-127">Devuelve la dirección URL de este documento.</span><span class="sxs-lookup"><span data-stu-id="e1eb7-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="e1eb7-128">HasEmbeddedSource (método)</span><span class="sxs-lookup"><span data-stu-id="e1eb7-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="e1eb7-129">Devuelve `true` si el documento tiene código fuente incrustado en los símbolos de depuración; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="e1eb7-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1eb7-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1eb7-130">See also</span></span>

- [<span data-ttu-id="e1eb7-131">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="e1eb7-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
