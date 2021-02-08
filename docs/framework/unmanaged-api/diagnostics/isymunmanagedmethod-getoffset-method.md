---
description: 'Más información sobre: ISymUnmanagedMethod:: GetOffset (método)'
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
ms.openlocfilehash: 3bc7154a47a38fd2cbadc62921f6e57f7901087e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790131"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="47a52-103">ISymUnmanagedMethod::GetOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="47a52-103">ISymUnmanagedMethod::GetOffset Method</span></span>

<span data-ttu-id="47a52-104">Devuelve el desplazamiento dentro de este método que corresponde a una posición determinada dentro de un documento.</span><span class="sxs-lookup"><span data-stu-id="47a52-104">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47a52-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47a52-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47a52-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47a52-106">Parameters</span></span>  

 `document`  
 <span data-ttu-id="47a52-107">de Un puntero al documento para el que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="47a52-107">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="47a52-108">de Línea del documento para la que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="47a52-108">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="47a52-109">de Columna del documento para la que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="47a52-109">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="47a52-110">enuncia Un puntero a un `ULONG32` que recibe los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="47a52-110">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47a52-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="47a52-111">Return Value</span></span>  

 <span data-ttu-id="47a52-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="47a52-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47a52-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47a52-113">Requirements</span></span>  

 <span data-ttu-id="47a52-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="47a52-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a52-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="47a52-115">See also</span></span>

- [<span data-ttu-id="47a52-116">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="47a52-116">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
