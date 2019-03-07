---
title: ISymUnmanagedWriter3::OpenMethod2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.OpenMethod2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 14a8acc2e3babd376cb9754d35ce8fc5eaa1fd7c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492327"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="30fd9-102">ISymUnmanagedWriter3::OpenMethod2 (Método)</span><span class="sxs-lookup"><span data-stu-id="30fd9-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="30fd9-103">Abre un método y proporciona su desplazamiento de sección real en la imagen.</span><span class="sxs-lookup"><span data-stu-id="30fd9-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30fd9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30fd9-104">Syntax</span></span>  
  
```  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30fd9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30fd9-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="30fd9-106">[in] El token de metadatos para el método que se puede abrir.</span><span class="sxs-lookup"><span data-stu-id="30fd9-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="30fd9-107">[in] El desplazamiento de sección en la imagen.</span><span class="sxs-lookup"><span data-stu-id="30fd9-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="30fd9-108">[in] El desplazamiento en la imagen.</span><span class="sxs-lookup"><span data-stu-id="30fd9-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30fd9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="30fd9-109">Return Value</span></span>  
 <span data-ttu-id="30fd9-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="30fd9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30fd9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30fd9-111">Requirements</span></span>  
 <span data-ttu-id="30fd9-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="30fd9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30fd9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="30fd9-113">See also</span></span>
- [<span data-ttu-id="30fd9-114">ISymUnmanagedWriter3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30fd9-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="30fd9-115">OpenMethod (método)</span><span class="sxs-lookup"><span data-stu-id="30fd9-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
