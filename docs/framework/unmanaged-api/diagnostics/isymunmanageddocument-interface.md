---
description: 'Más información acerca de: ISymUnmanagedDocument (interfaz)'
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
ms.openlocfilehash: cd1907e570dd15ebcac3ee12aa09c626c9bb7787
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710145"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="edceb-103">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="edceb-103">ISymUnmanagedDocument Interface</span></span>

<span data-ttu-id="edceb-104">Representa un documento al que hace referencia un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="edceb-104">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="edceb-105">Un documento se define mediante un localizador uniforme de recursos (URL) y un GUID de tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="edceb-105">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="edceb-106">Puede buscar el documento sin tener en consideración cómo se almacena mediante la dirección URL y el GUID del tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="edceb-106">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="edceb-107">Puede almacenar el origen del documento en el almacén de símbolos y recuperarlo a través de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="edceb-107">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="edceb-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="edceb-108">Methods</span></span>  
  
|<span data-ttu-id="edceb-109">Método</span><span class="sxs-lookup"><span data-stu-id="edceb-109">Method</span></span>|<span data-ttu-id="edceb-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="edceb-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="edceb-111">Método FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="edceb-111">FindClosestLine Method</span></span>](isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="edceb-112">Devuelve la línea más cercana que es un punto de secuencia, dada una línea de este documento que puede ser o no un punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="edceb-112">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="edceb-113">Método GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="edceb-113">GetCheckSum Method</span></span>](isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="edceb-114">Obtiene la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="edceb-114">Gets the checksum.</span></span>|  
|[<span data-ttu-id="edceb-115">Método GetCheckSumAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="edceb-115">GetCheckSumAlgorithmId Method</span></span>](isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="edceb-116">Obtiene el identificador del algoritmo de suma de comprobación o devuelve un GUID de todos los ceros si no hay ninguna suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="edceb-116">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="edceb-117">Método GetDocumentType</span><span class="sxs-lookup"><span data-stu-id="edceb-117">GetDocumentType Method</span></span>](isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="edceb-118">Obtiene el tipo de documento de este documento.</span><span class="sxs-lookup"><span data-stu-id="edceb-118">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="edceb-119">Método GetLanguage</span><span class="sxs-lookup"><span data-stu-id="edceb-119">GetLanguage Method</span></span>](isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="edceb-120">Obtiene el identificador de idioma de este documento.</span><span class="sxs-lookup"><span data-stu-id="edceb-120">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="edceb-121">Método GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="edceb-121">GetLanguageVendor Method</span></span>](isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="edceb-122">Obtiene el proveedor de lenguaje de este documento.</span><span class="sxs-lookup"><span data-stu-id="edceb-122">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="edceb-123">Método GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="edceb-123">GetSourceLength Method</span></span>](isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="edceb-124">Obtiene la longitud, en bytes, del código fuente incrustado.</span><span class="sxs-lookup"><span data-stu-id="edceb-124">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="edceb-125">Método GetSourceRange</span><span class="sxs-lookup"><span data-stu-id="edceb-125">GetSourceRange Method</span></span>](isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="edceb-126">Devuelve el intervalo especificado del código fuente incrustado en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="edceb-126">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="edceb-127">Método GetURL</span><span class="sxs-lookup"><span data-stu-id="edceb-127">GetURL Method</span></span>](isymunmanageddocument-geturl-method.md)|<span data-ttu-id="edceb-128">Devuelve la dirección URL de este documento.</span><span class="sxs-lookup"><span data-stu-id="edceb-128">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="edceb-129">Método HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="edceb-129">HasEmbeddedSource Method</span></span>](isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="edceb-130">Devuelve `true` si el documento tiene código fuente incrustado en los símbolos de depuración; de lo contrario, devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="edceb-130">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="edceb-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="edceb-131">See also</span></span>

- [<span data-ttu-id="edceb-132">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="edceb-132">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
