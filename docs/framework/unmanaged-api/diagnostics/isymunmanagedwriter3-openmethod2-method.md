---
description: 'Más información sobre: ISymUnmanagedWriter3:: Openmethod2 ((método)'
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
ms.openlocfilehash: 7e76be03598599a6498ed45bc3799c6d6f21e088
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761699"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="2f128-103">ISymUnmanagedWriter3::OpenMethod2 (Método)</span><span class="sxs-lookup"><span data-stu-id="2f128-103">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>

<span data-ttu-id="2f128-104">Abre un método y proporciona su desplazamiento de sección real en la imagen.</span><span class="sxs-lookup"><span data-stu-id="2f128-104">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f128-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f128-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f128-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2f128-106">Parameters</span></span>  

 `method`  
 <span data-ttu-id="2f128-107">de Símbolo (token) de metadatos para el método que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="2f128-107">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="2f128-108">de El desplazamiento de la sección en la imagen.</span><span class="sxs-lookup"><span data-stu-id="2f128-108">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="2f128-109">de Desplazamiento de la imagen.</span><span class="sxs-lookup"><span data-stu-id="2f128-109">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f128-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2f128-110">Return Value</span></span>  

 <span data-ttu-id="2f128-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="2f128-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f128-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f128-112">Requirements</span></span>  

 <span data-ttu-id="2f128-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2f128-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f128-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f128-114">See also</span></span>

- [<span data-ttu-id="2f128-115">ISymUnmanagedWriter3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2f128-115">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="2f128-116">Método OpenMethod</span><span class="sxs-lookup"><span data-stu-id="2f128-116">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
