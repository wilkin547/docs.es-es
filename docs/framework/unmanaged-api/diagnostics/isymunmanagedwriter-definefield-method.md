---
description: 'Más información acerca de: ISymUnmanagedWriter::D método efineField'
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
ms.openlocfilehash: f5bb47d4691780d94baf50cc9ceb3c14b1fa16ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762401"
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="67137-103">ISymUnmanagedWriter::DefineField (Método)</span><span class="sxs-lookup"><span data-stu-id="67137-103">ISymUnmanagedWriter::DefineField Method</span></span>

<span data-ttu-id="67137-104">Define una única variable que no está dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="67137-104">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="67137-105">Este método se usa para determinados campos de clases, campos de bits, etc.</span><span class="sxs-lookup"><span data-stu-id="67137-105">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67137-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67137-106">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="67137-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="67137-107">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="67137-108">de El tipo de metadatos o el token del método.</span><span class="sxs-lookup"><span data-stu-id="67137-108">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="67137-109">de Nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="67137-109">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="67137-110">de Atributos del campo.</span><span class="sxs-lookup"><span data-stu-id="67137-110">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="67137-111">de `ULONG32` Que es el tamaño, en caracteres, del búfer necesario para contener la firma del campo.</span><span class="sxs-lookup"><span data-stu-id="67137-111">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="67137-112">de Matriz de firmas de campo.</span><span class="sxs-lookup"><span data-stu-id="67137-112">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="67137-113">de Tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="67137-113">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="67137-114">de Primera dirección de la especificación de campo.</span><span class="sxs-lookup"><span data-stu-id="67137-114">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="67137-115">de Segunda dirección de la especificación de campo.</span><span class="sxs-lookup"><span data-stu-id="67137-115">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="67137-116">de Tercera dirección de la especificación de campo.</span><span class="sxs-lookup"><span data-stu-id="67137-116">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67137-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="67137-117">Return Value</span></span>  

 <span data-ttu-id="67137-118">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="67137-118">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67137-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67137-119">Requirements</span></span>  

 <span data-ttu-id="67137-120">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="67137-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67137-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="67137-121">See also</span></span>

- [<span data-ttu-id="67137-122">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="67137-122">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
