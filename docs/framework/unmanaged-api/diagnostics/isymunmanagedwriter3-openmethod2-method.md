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
ms.openlocfilehash: 3a628aec0823c5db07d31d33813a020606906163
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438129"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="6ed3b-102">ISymUnmanagedWriter3::OpenMethod2 (Método)</span><span class="sxs-lookup"><span data-stu-id="6ed3b-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="6ed3b-103">Abre un método y proporciona su desplazamiento de sección real en la imagen.</span><span class="sxs-lookup"><span data-stu-id="6ed3b-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ed3b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ed3b-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ed3b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6ed3b-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="6ed3b-106">de Símbolo (token) de metadatos para el método que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="6ed3b-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="6ed3b-107">de El desplazamiento de la sección en la imagen.</span><span class="sxs-lookup"><span data-stu-id="6ed3b-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="6ed3b-108">de Desplazamiento de la imagen.</span><span class="sxs-lookup"><span data-stu-id="6ed3b-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ed3b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6ed3b-109">Return Value</span></span>  
 <span data-ttu-id="6ed3b-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="6ed3b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ed3b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ed3b-111">Requirements</span></span>  
 <span data-ttu-id="6ed3b-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="6ed3b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ed3b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ed3b-113">See also</span></span>

- [<span data-ttu-id="6ed3b-114">ISymUnmanagedWriter3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ed3b-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="6ed3b-115">OpenMethod (método)</span><span class="sxs-lookup"><span data-stu-id="6ed3b-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
