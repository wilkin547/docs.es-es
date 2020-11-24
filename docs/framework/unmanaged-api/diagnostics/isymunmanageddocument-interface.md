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
ms.openlocfilehash: 83c683e1f60f13f7cee4ddc6fe5af5a94e36eb93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692181"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="f5e48-102">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5e48-102">ISymUnmanagedDocument Interface</span></span>

<span data-ttu-id="f5e48-103">Representa un documento al que hace referencia un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="f5e48-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="f5e48-104">Un documento se define mediante un localizador uniforme de recursos (URL) y un GUID de tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="f5e48-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="f5e48-105">Puede buscar el documento sin tener en consideración cómo se almacena mediante la dirección URL y el GUID del tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="f5e48-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="f5e48-106">Puede almacenar el origen del documento en el almacén de símbolos y recuperarlo a través de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="f5e48-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f5e48-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="f5e48-107">Methods</span></span>  
  
|<span data-ttu-id="f5e48-108">Método</span><span class="sxs-lookup"><span data-stu-id="f5e48-108">Method</span></span>|<span data-ttu-id="f5e48-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5e48-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f5e48-110">Método FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="f5e48-110">FindClosestLine Method</span></span>](isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="f5e48-111">Devuelve la línea más cercana que es un punto de secuencia, dada una línea de este documento que puede ser o no un punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="f5e48-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="f5e48-112">Método GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="f5e48-112">GetCheckSum Method</span></span>](isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="f5e48-113">Obtiene la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="f5e48-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="f5e48-114">Método GetCheckSumAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="f5e48-114">GetCheckSumAlgorithmId Method</span></span>](isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="f5e48-115">Obtiene el identificador del algoritmo de suma de comprobación o devuelve un GUID de todos los ceros si no hay ninguna suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="f5e48-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="f5e48-116">Método GetDocumentType</span><span class="sxs-lookup"><span data-stu-id="f5e48-116">GetDocumentType Method</span></span>](isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="f5e48-117">Obtiene el tipo de documento de este documento.</span><span class="sxs-lookup"><span data-stu-id="f5e48-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="f5e48-118">Método GetLanguage</span><span class="sxs-lookup"><span data-stu-id="f5e48-118">GetLanguage Method</span></span>](isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="f5e48-119">Obtiene el identificador de idioma de este documento.</span><span class="sxs-lookup"><span data-stu-id="f5e48-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="f5e48-120">Método GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="f5e48-120">GetLanguageVendor Method</span></span>](isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="f5e48-121">Obtiene el proveedor de lenguaje de este documento.</span><span class="sxs-lookup"><span data-stu-id="f5e48-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="f5e48-122">Método GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="f5e48-122">GetSourceLength Method</span></span>](isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="f5e48-123">Obtiene la longitud, en bytes, del código fuente incrustado.</span><span class="sxs-lookup"><span data-stu-id="f5e48-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="f5e48-124">Método GetSourceRange</span><span class="sxs-lookup"><span data-stu-id="f5e48-124">GetSourceRange Method</span></span>](isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="f5e48-125">Devuelve el intervalo especificado del código fuente incrustado en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="f5e48-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="f5e48-126">Método GetURL</span><span class="sxs-lookup"><span data-stu-id="f5e48-126">GetURL Method</span></span>](isymunmanageddocument-geturl-method.md)|<span data-ttu-id="f5e48-127">Devuelve la dirección URL de este documento.</span><span class="sxs-lookup"><span data-stu-id="f5e48-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="f5e48-128">Método HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="f5e48-128">HasEmbeddedSource Method</span></span>](isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="f5e48-129">Devuelve `true` si el documento tiene código fuente incrustado en los símbolos de depuración; de lo contrario, devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="f5e48-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5e48-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5e48-130">See also</span></span>

- [<span data-ttu-id="f5e48-131">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="f5e48-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
