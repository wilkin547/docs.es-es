---
title: ISymUnmanagedReader2::GetMethodByVersionPreRemap (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
ms.openlocfilehash: 5484242562deaf463b7435ad4e54735a7abee45e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730492"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="41a17-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap (Método)</span><span class="sxs-lookup"><span data-stu-id="41a17-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>

<span data-ttu-id="41a17-103">Obtiene un método del lector de símbolos, dado un token de método y un número de versión de edición y continuación.</span><span class="sxs-lookup"><span data-stu-id="41a17-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="41a17-104">Los números de versión se inician en 1 y se incrementan cada vez que se cambia el método como resultado de una operación de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="41a17-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41a17-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41a17-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41a17-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41a17-106">Parameters</span></span>  

 `token`  
 <span data-ttu-id="41a17-107">de Token de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="41a17-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="41a17-108">de Versión del método.</span><span class="sxs-lookup"><span data-stu-id="41a17-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="41a17-109">enuncia Puntero a la interfaz [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="41a17-109">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41a17-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="41a17-110">Return Value</span></span>  

 <span data-ttu-id="41a17-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="41a17-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41a17-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41a17-112">Requirements</span></span>  

 <span data-ttu-id="41a17-113">**Encabezado:** CorSym. idl.</span><span class="sxs-lookup"><span data-stu-id="41a17-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="41a17-114">CorSym. h</span><span class="sxs-lookup"><span data-stu-id="41a17-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a17-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="41a17-115">See also</span></span>

- [<span data-ttu-id="41a17-116">ISymUnmanagedReader2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="41a17-116">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
