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
ms.openlocfilehash: acb8d48ed6314756e2c1a10fff314a303799fb24
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707287"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="2e385-102">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e385-102">ISymENCUnmanagedMethod Interface</span></span>

<span data-ttu-id="2e385-103">Proporciona información para la característica editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="2e385-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2e385-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2e385-104">Methods</span></span>  
  
|<span data-ttu-id="2e385-105">Método</span><span class="sxs-lookup"><span data-stu-id="2e385-105">Method</span></span>|<span data-ttu-id="2e385-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e385-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e385-107">Método GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="2e385-107">GetDocumentsForMethod Method</span></span>](isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="2e385-108">Obtiene los documentos en los que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="2e385-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="2e385-109">Método GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="2e385-109">GetDocumentsForMethodCount Method</span></span>](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="2e385-110">Obtiene el número de documentos en los que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="2e385-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="2e385-111">Método GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="2e385-111">GetFileNameFromOffset Method</span></span>](isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="2e385-112">Obtiene el nombre de archivo de la línea asociada a un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="2e385-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="2e385-113">Método GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="2e385-113">GetLineFromOffset Method</span></span>](isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="2e385-114">Obtiene la información de línea asociada a un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="2e385-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="2e385-115">Método GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="2e385-115">GetSourceExtentInDocument Method</span></span>](isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="2e385-116">Obtiene la línea de inicio más pequeña y la línea de finalización más grande para el método en un documento específico.</span><span class="sxs-lookup"><span data-stu-id="2e385-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e385-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e385-117">Requirements</span></span>  

 <span data-ttu-id="2e385-118">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2e385-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e385-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e385-119">See also</span></span>

- [<span data-ttu-id="2e385-120">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="2e385-120">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
