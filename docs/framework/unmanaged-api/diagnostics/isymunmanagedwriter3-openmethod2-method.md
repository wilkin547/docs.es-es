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
ms.openlocfilehash: a3dcb1327ad50761a8268e8adc7b1e976cae0b3a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200303"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="4bb20-102">ISymUnmanagedWriter3::OpenMethod2 (Método)</span><span class="sxs-lookup"><span data-stu-id="4bb20-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="4bb20-103">Abre un método y proporciona su desplazamiento de sección real en la imagen.</span><span class="sxs-lookup"><span data-stu-id="4bb20-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bb20-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bb20-104">Syntax</span></span>  
  
```  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bb20-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4bb20-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="4bb20-106">[in] El token de metadatos para el método que se puede abrir.</span><span class="sxs-lookup"><span data-stu-id="4bb20-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="4bb20-107">[in] El desplazamiento de sección en la imagen.</span><span class="sxs-lookup"><span data-stu-id="4bb20-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="4bb20-108">[in] El desplazamiento en la imagen.</span><span class="sxs-lookup"><span data-stu-id="4bb20-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4bb20-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4bb20-109">Return Value</span></span>  
 <span data-ttu-id="4bb20-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="4bb20-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bb20-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4bb20-111">Requirements</span></span>  
 <span data-ttu-id="4bb20-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4bb20-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bb20-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bb20-113">See also</span></span>

- [<span data-ttu-id="4bb20-114">ISymUnmanagedWriter3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4bb20-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="4bb20-115">Método OpenMethod</span><span class="sxs-lookup"><span data-stu-id="4bb20-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
