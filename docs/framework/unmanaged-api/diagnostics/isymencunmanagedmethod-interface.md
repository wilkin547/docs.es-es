---
title: ISymENCUnmanagedMethod (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f46aeed0a303278fd67265e471bfa13b43cede12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680204"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="493bd-102">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="493bd-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="493bd-103">Proporciona información para la característica Editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="493bd-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="493bd-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="493bd-104">Methods</span></span>  
  
|<span data-ttu-id="493bd-105">Método</span><span class="sxs-lookup"><span data-stu-id="493bd-105">Method</span></span>|<span data-ttu-id="493bd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="493bd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="493bd-107">GetDocumentsForMethod (método)</span><span class="sxs-lookup"><span data-stu-id="493bd-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="493bd-108">Obtiene los documentos que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="493bd-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="493bd-109">GetDocumentsForMethodCount (método)</span><span class="sxs-lookup"><span data-stu-id="493bd-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="493bd-110">Obtiene el número de documentos que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="493bd-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="493bd-111">GetFileNameFromOffset (método)</span><span class="sxs-lookup"><span data-stu-id="493bd-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="493bd-112">Obtiene el nombre de archivo de la línea asociada con un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="493bd-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="493bd-113">GetLineFromOffset (método)</span><span class="sxs-lookup"><span data-stu-id="493bd-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="493bd-114">Obtiene la información de línea asociada con un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="493bd-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="493bd-115">GetSourceExtentInDocument (método)</span><span class="sxs-lookup"><span data-stu-id="493bd-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="493bd-116">Obtiene el valor más pequeño inicia línea y más grande fin de línea para el método en un documento específico.</span><span class="sxs-lookup"><span data-stu-id="493bd-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="493bd-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="493bd-117">Requirements</span></span>  
 <span data-ttu-id="493bd-118">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="493bd-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="493bd-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="493bd-119">See also</span></span>
- [<span data-ttu-id="493bd-120">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="493bd-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
