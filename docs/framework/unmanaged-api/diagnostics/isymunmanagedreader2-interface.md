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
ms.openlocfilehash: a08695c4e5df6aaa63bedecf68b741302e5ddd8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524952"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="a9163-102">ISymUnmanagedReader2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9163-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="a9163-103">Representa un lector de símbolos que proporciona acceso a documentos, métodos y variables dentro de un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="a9163-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="a9163-104">Esta interfaz extiende la [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="a9163-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9163-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a9163-105">Methods</span></span>  
  
|<span data-ttu-id="a9163-106">Método</span><span class="sxs-lookup"><span data-stu-id="a9163-106">Method</span></span>|<span data-ttu-id="a9163-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9163-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9163-108">GetMethodByVersionPreRemap (método)</span><span class="sxs-lookup"><span data-stu-id="a9163-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="a9163-109">Obtiene un método del lector de símbolos, dados un token de método y un número de versión de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="a9163-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="a9163-110">GetMethodsInDocument (método)</span><span class="sxs-lookup"><span data-stu-id="a9163-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="a9163-111">Obtiene todos los métodos que tiene información de línea en el documento proporcionado.</span><span class="sxs-lookup"><span data-stu-id="a9163-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="a9163-112">GetSymAttributePreRemap (método)</span><span class="sxs-lookup"><span data-stu-id="a9163-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="a9163-113">Obtiene un atributo personalizado basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="a9163-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9163-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9163-114">Requirements</span></span>  
 <span data-ttu-id="a9163-115">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a9163-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9163-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9163-116">See also</span></span>
- [<span data-ttu-id="a9163-117">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="a9163-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="a9163-118">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9163-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
