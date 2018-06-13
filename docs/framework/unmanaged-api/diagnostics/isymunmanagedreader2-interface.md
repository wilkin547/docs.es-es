---
title: ISymUnmanagedReader2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1dfc67ecf1eeb9ea5a19c98a8c378e73021da6c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426833"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="aa86d-102">ISymUnmanagedReader2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa86d-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="aa86d-103">Representa un lector de símbolos que proporciona acceso a documentos, métodos y variables del sistema en un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="aa86d-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="aa86d-104">Esta interfaz extiende la [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="aa86d-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa86d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="aa86d-105">Methods</span></span>  
  
|<span data-ttu-id="aa86d-106">Método</span><span class="sxs-lookup"><span data-stu-id="aa86d-106">Method</span></span>|<span data-ttu-id="aa86d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa86d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa86d-108">GetMethodByVersionPreRemap (método)</span><span class="sxs-lookup"><span data-stu-id="aa86d-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="aa86d-109">Obtener un método del lector de símbolos, dados un token de método y un número de versión de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="aa86d-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="aa86d-110">GetMethodsInDocument (método)</span><span class="sxs-lookup"><span data-stu-id="aa86d-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="aa86d-111">Obtiene cada método que tiene información de línea en el documento proporcionado.</span><span class="sxs-lookup"><span data-stu-id="aa86d-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="aa86d-112">GetSymAttributePreRemap (método)</span><span class="sxs-lookup"><span data-stu-id="aa86d-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="aa86d-113">Obtiene un atributo personalizado basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="aa86d-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa86d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa86d-114">Requirements</span></span>  
 <span data-ttu-id="aa86d-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="aa86d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa86d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa86d-116">See Also</span></span>  
 [<span data-ttu-id="aa86d-117">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="aa86d-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="aa86d-118">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa86d-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
