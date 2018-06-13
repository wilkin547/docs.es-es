---
title: ISymUnmanagedReader2::GetSymAttributePreRemap (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 326f970f53293b74bbf8c5e77830f3f6ce1b73ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427042"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a><span data-ttu-id="88fff-102">ISymUnmanagedReader2::GetSymAttributePreRemap (Método)</span><span class="sxs-lookup"><span data-stu-id="88fff-102">ISymUnmanagedReader2::GetSymAttributePreRemap Method</span></span>
<span data-ttu-id="88fff-103">Obtiene un atributo personalizado basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="88fff-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="88fff-104">A diferencia de los atributos personalizados de metadatos, estos atributos se encuentran en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="88fff-104">Unlike metadata custom attributes, these attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88fff-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88fff-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88fff-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="88fff-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="88fff-107">[in] El token de metadatos del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="88fff-107">[in] The metadata token of the parent.</span></span>  
  
 `name`  
 <span data-ttu-id="88fff-108">[in] Un puntero a un `WCHAR` que contiene el nombre.</span><span class="sxs-lookup"><span data-stu-id="88fff-108">[in] A pointer to a `WCHAR` that contains the name.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="88fff-109">[in] A `ULONG32` que indica el tamaño de la `buffer` matriz.</span><span class="sxs-lookup"><span data-stu-id="88fff-109">[in] A `ULONG32` that indicates the size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="88fff-110">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los bytes del atributo.</span><span class="sxs-lookup"><span data-stu-id="88fff-110">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the attribute bytes.</span></span>  
  
 `buffer`  
 <span data-ttu-id="88fff-111">[out] Un puntero al búfer que recibe los bytes del atributo.</span><span class="sxs-lookup"><span data-stu-id="88fff-111">[out] A pointer to the buffer that receives the attribute bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88fff-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="88fff-112">Return Value</span></span>  
 <span data-ttu-id="88fff-113">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="88fff-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88fff-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88fff-114">Requirements</span></span>  
 <span data-ttu-id="88fff-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="88fff-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88fff-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="88fff-116">See Also</span></span>  
 [<span data-ttu-id="88fff-117">ISymUnmanagedReader2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="88fff-117">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
