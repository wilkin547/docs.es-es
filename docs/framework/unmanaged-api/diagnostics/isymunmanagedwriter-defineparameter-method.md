---
title: ISymUnmanagedWriter::DefineParameter (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5b82415635980f5bd4e13e87a0a03ec5b7032bb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777327"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="f28d0-102">ISymUnmanagedWriter::DefineParameter (Método)</span><span class="sxs-lookup"><span data-stu-id="f28d0-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="f28d0-103">Define un único parámetro del método actual.</span><span class="sxs-lookup"><span data-stu-id="f28d0-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="f28d0-104">El tipo de parámetro procede de la posición del parámetro (secuencia) dentro de la firma del método.</span><span class="sxs-lookup"><span data-stu-id="f28d0-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="f28d0-105">Si los parámetros se definen en los metadatos de un método determinado, no tiene que definir de nuevo mediante el uso de este método.</span><span class="sxs-lookup"><span data-stu-id="f28d0-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="f28d0-106">Los lectores de símbolos deben comprobar los metadatos para los parámetros normales antes de comprobar el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="f28d0-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f28d0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f28d0-107">Syntax</span></span>  
  
```cpp  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f28d0-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f28d0-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f28d0-109">[in] El nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="f28d0-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="f28d0-110">[in] Los atributos de parámetro.</span><span class="sxs-lookup"><span data-stu-id="f28d0-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="f28d0-111">[in] La firma del parámetro.</span><span class="sxs-lookup"><span data-stu-id="f28d0-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="f28d0-112">[in] El tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="f28d0-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="f28d0-113">[in] La primera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="f28d0-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="f28d0-114">[in] La segunda dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="f28d0-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="f28d0-115">[in] Tercera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="f28d0-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f28d0-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f28d0-116">Return Value</span></span>  
 <span data-ttu-id="f28d0-117">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f28d0-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f28d0-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f28d0-118">Requirements</span></span>  
 <span data-ttu-id="f28d0-119">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f28d0-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f28d0-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f28d0-120">See also</span></span>

- [<span data-ttu-id="f28d0-121">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f28d0-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
