---
description: 'Más información acerca de: ISymUnmanagedWriter2::D efineConstant2 (método)'
title: ISymUnmanagedWriter2::DefineConstant2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
ms.openlocfilehash: 9a0c444909055e18bdcd0b54fefbc8534ff8681e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761933"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="7b7cd-103">ISymUnmanagedWriter2::DefineConstant2 (Método)</span><span class="sxs-lookup"><span data-stu-id="7b7cd-103">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>

<span data-ttu-id="7b7cd-104">Define un nombre para un valor constante.</span><span class="sxs-lookup"><span data-stu-id="7b7cd-104">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b7cd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b7cd-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b7cd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b7cd-106">Parameters</span></span>  

 `name`  
 <span data-ttu-id="7b7cd-107">de El nombre de la constante.</span><span class="sxs-lookup"><span data-stu-id="7b7cd-107">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="7b7cd-108">de Valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="7b7cd-108">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="7b7cd-109">de Símbolo (token) de metadatos de la constante.</span><span class="sxs-lookup"><span data-stu-id="7b7cd-109">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b7cd-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7b7cd-110">Return Value</span></span>  

 <span data-ttu-id="7b7cd-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="7b7cd-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b7cd-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b7cd-112">Requirements</span></span>  

 <span data-ttu-id="7b7cd-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7b7cd-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b7cd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b7cd-114">See also</span></span>

- [<span data-ttu-id="7b7cd-115">ISymUnmanagedWriter2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b7cd-115">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="7b7cd-116">Método DefineConstant</span><span class="sxs-lookup"><span data-stu-id="7b7cd-116">DefineConstant Method</span></span>](isymunmanagedwriter-defineconstant-method.md)
