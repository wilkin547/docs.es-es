---
title: ISymUnmanagedWriter::SetSymAttribute (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd1a55d4100d74b769b2bc1b8fe33d2042f5e739
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428306"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="2fbf7-102">ISymUnmanagedWriter::SetSymAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="2fbf7-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="2fbf7-103">Define un atributo personalizado basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="2fbf7-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="2fbf7-104">Estos atributos se encuentran en el almacén de símbolos, a diferencia de los atributos personalizados de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2fbf7-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fbf7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2fbf7-105">Syntax</span></span>  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2fbf7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2fbf7-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="2fbf7-107">[in] El token de metadatos para el que se está definiendo el atributo.</span><span class="sxs-lookup"><span data-stu-id="2fbf7-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="2fbf7-108">[in] Un puntero a un `WCHAR` que contiene el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="2fbf7-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="2fbf7-109">[in] A `ULONG32` que indica el tamaño de la `data` matriz.</span><span class="sxs-lookup"><span data-stu-id="2fbf7-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="2fbf7-110">[in] El valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="2fbf7-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fbf7-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2fbf7-111">Return Value</span></span>  
 <span data-ttu-id="2fbf7-112">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="2fbf7-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fbf7-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2fbf7-113">Requirements</span></span>  
 <span data-ttu-id="2fbf7-114">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2fbf7-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fbf7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fbf7-115">See Also</span></span>  
 [<span data-ttu-id="2fbf7-116">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2fbf7-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
