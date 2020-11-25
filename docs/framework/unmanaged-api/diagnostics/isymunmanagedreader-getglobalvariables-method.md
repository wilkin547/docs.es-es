---
title: ISymUnmanagedReader::GetGlobalVariables (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetGlobalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type:
- apiref
ms.openlocfilehash: 299787ea4eb8a5c25bdab64ad08445839c9f24d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707547"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="685b5-102">ISymUnmanagedReader::GetGlobalVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="685b5-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>

<span data-ttu-id="685b5-103">Devuelve todas las variables globales.</span><span class="sxs-lookup"><span data-stu-id="685b5-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="685b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="685b5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="685b5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="685b5-105">Parameters</span></span>  

 `cVars`  
 <span data-ttu-id="685b5-106">de Longitud del búfer al que apunta `pcVars` .</span><span class="sxs-lookup"><span data-stu-id="685b5-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="685b5-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener las variables.</span><span class="sxs-lookup"><span data-stu-id="685b5-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="685b5-108">enuncia Búfer que contiene las variables.</span><span class="sxs-lookup"><span data-stu-id="685b5-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="685b5-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="685b5-109">Return Value</span></span>  

 <span data-ttu-id="685b5-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="685b5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="685b5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="685b5-111">Requirements</span></span>  

 <span data-ttu-id="685b5-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="685b5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="685b5-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="685b5-113">See also</span></span>

- [<span data-ttu-id="685b5-114">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="685b5-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
