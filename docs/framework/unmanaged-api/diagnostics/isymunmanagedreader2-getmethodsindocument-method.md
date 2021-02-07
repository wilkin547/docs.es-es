---
description: 'Más información sobre: ISymUnmanagedReader2:: Getmethodsindocument ((método)'
title: ISymUnmanagedReader2::GetMethodsInDocument (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
ms.openlocfilehash: 1f75594a479edbf2e0160c9d3543384c0cbf68a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763688"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="5a88b-103">ISymUnmanagedReader2::GetMethodsInDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="5a88b-103">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>

<span data-ttu-id="5a88b-104">Obtiene todos los métodos que tienen información de línea en el documento proporcionado.</span><span class="sxs-lookup"><span data-stu-id="5a88b-104">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a88b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a88b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a88b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a88b-106">Parameters</span></span>  

 `document`  
 <span data-ttu-id="5a88b-107">de Puntero al documento.</span><span class="sxs-lookup"><span data-stu-id="5a88b-107">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="5a88b-108">de `ULONG32` Que indica el tamaño de la  `pRetVal` matriz.</span><span class="sxs-lookup"><span data-stu-id="5a88b-108">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="5a88b-109">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los métodos.</span><span class="sxs-lookup"><span data-stu-id="5a88b-109">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="5a88b-110">enuncia Puntero al búfer que recibe los métodos.</span><span class="sxs-lookup"><span data-stu-id="5a88b-110">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a88b-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5a88b-111">Return Value</span></span>  

 <span data-ttu-id="5a88b-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="5a88b-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a88b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a88b-113">Requirements</span></span>  

 <span data-ttu-id="5a88b-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5a88b-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a88b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a88b-115">See also</span></span>

- [<span data-ttu-id="5a88b-116">ISymUnmanagedReader2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a88b-116">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
