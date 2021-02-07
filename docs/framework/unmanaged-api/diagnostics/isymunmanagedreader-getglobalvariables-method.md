---
description: 'Más información acerca de: ISymUnmanagedReader:: GetGlobalVariables ((método)'
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
ms.openlocfilehash: 2b017d2a5746942f701cf79d3d29f1eb571dceab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689656"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="432c4-103">ISymUnmanagedReader::GetGlobalVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="432c4-103">ISymUnmanagedReader::GetGlobalVariables Method</span></span>

<span data-ttu-id="432c4-104">Devuelve todas las variables globales.</span><span class="sxs-lookup"><span data-stu-id="432c4-104">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="432c4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="432c4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="432c4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="432c4-106">Parameters</span></span>  

 `cVars`  
 <span data-ttu-id="432c4-107">de Longitud del búfer al que apunta `pcVars` .</span><span class="sxs-lookup"><span data-stu-id="432c4-107">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="432c4-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener las variables.</span><span class="sxs-lookup"><span data-stu-id="432c4-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="432c4-109">enuncia Búfer que contiene las variables.</span><span class="sxs-lookup"><span data-stu-id="432c4-109">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="432c4-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="432c4-110">Return Value</span></span>  

 <span data-ttu-id="432c4-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="432c4-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="432c4-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="432c4-112">Requirements</span></span>  

 <span data-ttu-id="432c4-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="432c4-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="432c4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="432c4-114">See also</span></span>

- [<span data-ttu-id="432c4-115">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="432c4-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
