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
ms.openlocfilehash: 54c8c7f5c3ba6b4afd4ff352a8afb947a92e2d61
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441882"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="53513-102">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="53513-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="53513-103">Proporciona información para la característica editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="53513-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53513-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="53513-104">Methods</span></span>  
  
|<span data-ttu-id="53513-105">Método</span><span class="sxs-lookup"><span data-stu-id="53513-105">Method</span></span>|<span data-ttu-id="53513-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="53513-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53513-107">Método GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="53513-107">GetDocumentsForMethod Method</span></span>](isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="53513-108">Obtiene los documentos en los que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="53513-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="53513-109">Método GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="53513-109">GetDocumentsForMethodCount Method</span></span>](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="53513-110">Obtiene el número de documentos en los que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="53513-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="53513-111">Método GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="53513-111">GetFileNameFromOffset Method</span></span>](isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="53513-112">Obtiene el nombre de archivo de la línea asociada a un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="53513-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="53513-113">Método GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="53513-113">GetLineFromOffset Method</span></span>](isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="53513-114">Obtiene la información de línea asociada a un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="53513-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="53513-115">Método GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="53513-115">GetSourceExtentInDocument Method</span></span>](isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="53513-116">Obtiene la línea de inicio más pequeña y la línea de finalización más grande para el método en un documento específico.</span><span class="sxs-lookup"><span data-stu-id="53513-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53513-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53513-117">Requirements</span></span>  
 <span data-ttu-id="53513-118">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="53513-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53513-119">Consulta también</span><span class="sxs-lookup"><span data-stu-id="53513-119">See also</span></span>

- [<span data-ttu-id="53513-120">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="53513-120">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
