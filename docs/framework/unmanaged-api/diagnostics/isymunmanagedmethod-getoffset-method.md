---
title: ISymUnmanagedMethod::GetOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
ms.openlocfilehash: 358f3d3d7c231a2baa9d2c467935ba3a5867e36b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614479"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="e5273-102">ISymUnmanagedMethod::GetOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="e5273-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="e5273-103">Devuelve el desplazamiento dentro de este método que corresponde a una posición determinada dentro de un documento.</span><span class="sxs-lookup"><span data-stu-id="e5273-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5273-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5273-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5273-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5273-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="e5273-106">de Un puntero al documento para el que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="e5273-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="e5273-107">de Línea del documento para la que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="e5273-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="e5273-108">de Columna del documento para la que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="e5273-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e5273-109">enuncia Un puntero a un `ULONG32` que recibe los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="e5273-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5273-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e5273-110">Return Value</span></span>  
 <span data-ttu-id="e5273-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e5273-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5273-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5273-112">Requirements</span></span>  
 <span data-ttu-id="e5273-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e5273-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5273-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="e5273-114">See also</span></span>

- [<span data-ttu-id="e5273-115">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5273-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
