---
description: 'Más información acerca de: interfaz ISymUnmanagedReader2'
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
ms.openlocfilehash: 2e6d994a3252b7fb09b2915266e3142255878a88
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763623"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="d0c90-103">ISymUnmanagedReader2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0c90-103">ISymUnmanagedReader2 Interface</span></span>

<span data-ttu-id="d0c90-104">Representa un lector de símbolos que proporciona acceso a los documentos, métodos y variables de un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="d0c90-104">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="d0c90-105">Esta interfaz extiende la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d0c90-105">This interface extends the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d0c90-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="d0c90-106">Methods</span></span>  
  
|<span data-ttu-id="d0c90-107">Método</span><span class="sxs-lookup"><span data-stu-id="d0c90-107">Method</span></span>|<span data-ttu-id="d0c90-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0c90-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d0c90-109">Método GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="d0c90-109">GetMethodByVersionPreRemap Method</span></span>](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="d0c90-110">Obtiene un método del lector de símbolos, dado un token de método y un número de versión de edición y continuación.</span><span class="sxs-lookup"><span data-stu-id="d0c90-110">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="d0c90-111">Método GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="d0c90-111">GetMethodsInDocument Method</span></span>](isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="d0c90-112">Obtiene todos los métodos que tienen información de línea en el documento proporcionado.</span><span class="sxs-lookup"><span data-stu-id="d0c90-112">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="d0c90-113">Método GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="d0c90-113">GetSymAttributePreRemap Method</span></span>](isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="d0c90-114">Obtiene un atributo personalizado basado en su nombre.</span><span class="sxs-lookup"><span data-stu-id="d0c90-114">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d0c90-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0c90-115">Requirements</span></span>  

 <span data-ttu-id="d0c90-116">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d0c90-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0c90-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0c90-117">See also</span></span>

- [<span data-ttu-id="d0c90-118">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="d0c90-118">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="d0c90-119">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0c90-119">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
