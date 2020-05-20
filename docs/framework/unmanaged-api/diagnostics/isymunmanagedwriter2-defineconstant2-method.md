---
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
ms.openlocfilehash: 70ee853ff657a75dcc4df1454c4354f9d3f8202f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614726"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="75ced-102">ISymUnmanagedWriter2::DefineConstant2 (Método)</span><span class="sxs-lookup"><span data-stu-id="75ced-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="75ced-103">Define un nombre para un valor constante.</span><span class="sxs-lookup"><span data-stu-id="75ced-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75ced-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75ced-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75ced-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75ced-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="75ced-106">de El nombre de la constante.</span><span class="sxs-lookup"><span data-stu-id="75ced-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="75ced-107">de Valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="75ced-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="75ced-108">de Símbolo (token) de metadatos de la constante.</span><span class="sxs-lookup"><span data-stu-id="75ced-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75ced-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="75ced-109">Return Value</span></span>  
 <span data-ttu-id="75ced-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="75ced-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75ced-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75ced-111">Requirements</span></span>  
 <span data-ttu-id="75ced-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="75ced-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ced-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="75ced-113">See also</span></span>

- [<span data-ttu-id="75ced-114">ISymUnmanagedWriter2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="75ced-114">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="75ced-115">Método DefineConstant</span><span class="sxs-lookup"><span data-stu-id="75ced-115">DefineConstant Method</span></span>](isymunmanagedwriter-defineconstant-method.md)
