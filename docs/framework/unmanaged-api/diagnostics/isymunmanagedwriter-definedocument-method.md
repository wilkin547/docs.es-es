---
description: 'Más información acerca de: ISymUnmanagedWriter::D método efineDocument'
title: ISymUnmanagedWriter::DefineDocument (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
ms.openlocfilehash: 35e918292e6ee50e17932645e003d19513e2397a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762544"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="cd97a-103">ISymUnmanagedWriter::DefineDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="cd97a-103">ISymUnmanagedWriter::DefineDocument Method</span></span>

<span data-ttu-id="cd97a-104">Define un documento de origen.</span><span class="sxs-lookup"><span data-stu-id="cd97a-104">Defines a source document.</span></span> <span data-ttu-id="cd97a-105">Se proporcionan GUID para los lenguajes, proveedores y tipos de documento conocidos.</span><span class="sxs-lookup"><span data-stu-id="cd97a-105">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd97a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd97a-106">Syntax</span></span>  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd97a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd97a-107">Parameters</span></span>  

 `url`  
 <span data-ttu-id="cd97a-108">de Un puntero a `WCHAR` que define el localizador uniforme de recursos (URL) que identifica el documento.</span><span class="sxs-lookup"><span data-stu-id="cd97a-108">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="cd97a-109">de Un puntero a un GUID que define el idioma del documento.</span><span class="sxs-lookup"><span data-stu-id="cd97a-109">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="cd97a-110">de Un puntero a un GUID que define la identidad del proveedor para el idioma del documento.</span><span class="sxs-lookup"><span data-stu-id="cd97a-110">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="cd97a-111">de Un puntero a un GUID que define el tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="cd97a-111">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="cd97a-112">enuncia Puntero a la interfaz [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="cd97a-112">[out] A pointer to the returned [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd97a-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cd97a-113">Return Value</span></span>  

 <span data-ttu-id="cd97a-114">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="cd97a-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd97a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd97a-115">Requirements</span></span>  

 <span data-ttu-id="cd97a-116">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="cd97a-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd97a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd97a-117">See also</span></span>

- [<span data-ttu-id="cd97a-118">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd97a-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
