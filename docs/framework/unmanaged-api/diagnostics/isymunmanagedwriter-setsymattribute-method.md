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
ms.openlocfilehash: 4450c262b75a73114cb7de7de98567f053bbf564
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894469"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="8455f-102">ISymUnmanagedWriter::SetSymAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="8455f-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="8455f-103">Define un atributo personalizado basado en su nombre.</span><span class="sxs-lookup"><span data-stu-id="8455f-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="8455f-104">Estos atributos se guardan en el almacén de símbolos, a diferencia de los atributos personalizados de metadatos.</span><span class="sxs-lookup"><span data-stu-id="8455f-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8455f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8455f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8455f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8455f-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="8455f-107">de Token de metadatos para el que se define el atributo.</span><span class="sxs-lookup"><span data-stu-id="8455f-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="8455f-108">de Un puntero a un `WCHAR` que contiene el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="8455f-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="8455f-109">de Que indica el tamaño de la `data` matriz. `ULONG32`</span><span class="sxs-lookup"><span data-stu-id="8455f-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="8455f-110">de Valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="8455f-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8455f-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8455f-111">Return Value</span></span>  
 <span data-ttu-id="8455f-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8455f-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8455f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8455f-113">Requirements</span></span>  
 <span data-ttu-id="8455f-114">**Encabezado**: CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8455f-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8455f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8455f-115">See also</span></span>

- [<span data-ttu-id="8455f-116">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8455f-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
