---
description: 'Más información acerca de: interfaz ISymENCUnmanagedMethod'
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
ms.openlocfilehash: 59dd56c20279b2507fc4432182d0abb5b3e9c289
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790326"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="73501-103">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="73501-103">ISymENCUnmanagedMethod Interface</span></span>

<span data-ttu-id="73501-104">Proporciona información para la característica editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="73501-104">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73501-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="73501-105">Methods</span></span>  
  
|<span data-ttu-id="73501-106">Método</span><span class="sxs-lookup"><span data-stu-id="73501-106">Method</span></span>|<span data-ttu-id="73501-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="73501-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73501-108">Método GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="73501-108">GetDocumentsForMethod Method</span></span>](isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="73501-109">Obtiene los documentos en los que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="73501-109">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="73501-110">Método GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="73501-110">GetDocumentsForMethodCount Method</span></span>](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="73501-111">Obtiene el número de documentos en los que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="73501-111">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="73501-112">Método GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="73501-112">GetFileNameFromOffset Method</span></span>](isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="73501-113">Obtiene el nombre de archivo de la línea asociada a un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="73501-113">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="73501-114">Método GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="73501-114">GetLineFromOffset Method</span></span>](isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="73501-115">Obtiene la información de línea asociada a un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="73501-115">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="73501-116">Método GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="73501-116">GetSourceExtentInDocument Method</span></span>](isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="73501-117">Obtiene la línea de inicio más pequeña y la línea de finalización más grande para el método en un documento específico.</span><span class="sxs-lookup"><span data-stu-id="73501-117">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73501-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73501-118">Requirements</span></span>  

 <span data-ttu-id="73501-119">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="73501-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73501-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="73501-120">See also</span></span>

- [<span data-ttu-id="73501-121">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="73501-121">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
