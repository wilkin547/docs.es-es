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
ms.openlocfilehash: 14d4211b208482a399aa00430791b3efffda851e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699552"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="3774c-102">ISymUnmanagedMethod::GetOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="3774c-102">ISymUnmanagedMethod::GetOffset Method</span></span>

<span data-ttu-id="3774c-103">Devuelve el desplazamiento dentro de este método que corresponde a una posición determinada dentro de un documento.</span><span class="sxs-lookup"><span data-stu-id="3774c-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3774c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3774c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3774c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3774c-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="3774c-106">de Un puntero al documento para el que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="3774c-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="3774c-107">de Línea del documento para la que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="3774c-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="3774c-108">de Columna del documento para la que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="3774c-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="3774c-109">enuncia Un puntero a un `ULONG32` que recibe los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="3774c-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3774c-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3774c-110">Return Value</span></span>  

 <span data-ttu-id="3774c-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="3774c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3774c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3774c-112">Requirements</span></span>  

 <span data-ttu-id="3774c-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3774c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3774c-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3774c-114">See also</span></span>

- [<span data-ttu-id="3774c-115">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3774c-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
