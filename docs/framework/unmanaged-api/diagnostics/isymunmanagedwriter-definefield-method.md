---
title: ISymUnmanagedWriter::DefineField (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5fd9798b3681d66e71d5703f4d16564b153da07b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789635"
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="97c65-102">ISymUnmanagedWriter::DefineField (Método)</span><span class="sxs-lookup"><span data-stu-id="97c65-102">ISymUnmanagedWriter::DefineField Method</span></span>
<span data-ttu-id="97c65-103">Define una única variable que no está dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="97c65-103">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="97c65-104">Este método es usados para ciertos campos en clases, campos de bits y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="97c65-104">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97c65-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97c65-105">Syntax</span></span>  
  
```  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97c65-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="97c65-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="97c65-107">[in] El tipo de metadatos o el método token.</span><span class="sxs-lookup"><span data-stu-id="97c65-107">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="97c65-108">[in] El nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="97c65-108">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="97c65-109">[in] Los atributos del campo.</span><span class="sxs-lookup"><span data-stu-id="97c65-109">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="97c65-110">[in] Un `ULONG32` que es el tamaño, en caracteres, del búfer necesario para contener la firma del campo.</span><span class="sxs-lookup"><span data-stu-id="97c65-110">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="97c65-111">[in] Matriz de firmas de campo.</span><span class="sxs-lookup"><span data-stu-id="97c65-111">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="97c65-112">[in] El tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="97c65-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="97c65-113">[in] La primera dirección de la especificación de campo.</span><span class="sxs-lookup"><span data-stu-id="97c65-113">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="97c65-114">[in] La segunda dirección de la especificación de campo.</span><span class="sxs-lookup"><span data-stu-id="97c65-114">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="97c65-115">[in] Tercera dirección de la especificación de campo.</span><span class="sxs-lookup"><span data-stu-id="97c65-115">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97c65-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="97c65-116">Return Value</span></span>  
 <span data-ttu-id="97c65-117">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="97c65-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97c65-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="97c65-118">Requirements</span></span>  
 <span data-ttu-id="97c65-119">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="97c65-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97c65-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="97c65-120">See also</span></span>

- [<span data-ttu-id="97c65-121">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="97c65-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
