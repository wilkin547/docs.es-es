---
description: 'Más información acerca de: ISymUnmanagedWriter:: SetSymAttribute ((método)'
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
ms.openlocfilehash: 0509e6430646fa67112b29d30d5053eb4a541415
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761998"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="e884c-103">ISymUnmanagedWriter::SetSymAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="e884c-103">ISymUnmanagedWriter::SetSymAttribute Method</span></span>

<span data-ttu-id="e884c-104">Define un atributo personalizado basado en su nombre.</span><span class="sxs-lookup"><span data-stu-id="e884c-104">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="e884c-105">Estos atributos se guardan en el almacén de símbolos, a diferencia de los atributos personalizados de metadatos.</span><span class="sxs-lookup"><span data-stu-id="e884c-105">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e884c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e884c-106">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e884c-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e884c-107">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="e884c-108">de Token de metadatos para el que se define el atributo.</span><span class="sxs-lookup"><span data-stu-id="e884c-108">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="e884c-109">de Un puntero a un `WCHAR` que contiene el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="e884c-109">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="e884c-110">de `ULONG32` Que indica el tamaño de la `data` matriz.</span><span class="sxs-lookup"><span data-stu-id="e884c-110">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="e884c-111">de Valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="e884c-111">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e884c-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e884c-112">Return Value</span></span>  

 <span data-ttu-id="e884c-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e884c-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e884c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e884c-114">Requirements</span></span>  

 <span data-ttu-id="e884c-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e884c-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e884c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e884c-116">See also</span></span>

- [<span data-ttu-id="e884c-117">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e884c-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
