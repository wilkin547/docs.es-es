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
ms.openlocfilehash: 890053e1bf2e0648a41cca718e94edcf21c7e612
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165989"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="97a28-102">ISymUnmanagedReader2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="97a28-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="97a28-103">Representa un lector de símbolos que proporciona acceso a documentos, métodos y variables dentro de un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="97a28-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="97a28-104">Esta interfaz extiende la [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="97a28-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97a28-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="97a28-105">Methods</span></span>  
  
|<span data-ttu-id="97a28-106">Método</span><span class="sxs-lookup"><span data-stu-id="97a28-106">Method</span></span>|<span data-ttu-id="97a28-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="97a28-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="97a28-108">Método GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="97a28-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="97a28-109">Obtiene un método del lector de símbolos, dados un token de método y un número de versión de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="97a28-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="97a28-110">Método GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="97a28-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="97a28-111">Obtiene todos los métodos que tiene información de línea en el documento proporcionado.</span><span class="sxs-lookup"><span data-stu-id="97a28-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="97a28-112">Método GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="97a28-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="97a28-113">Obtiene un atributo personalizado basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="97a28-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="97a28-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="97a28-114">Requirements</span></span>  
 <span data-ttu-id="97a28-115">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="97a28-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97a28-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="97a28-116">See also</span></span>

- [<span data-ttu-id="97a28-117">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="97a28-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="97a28-118">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="97a28-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
