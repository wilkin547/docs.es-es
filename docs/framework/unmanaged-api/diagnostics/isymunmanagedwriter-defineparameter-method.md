---
title: "ISymUnmanagedWriter::DefineParameter (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineParameter
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 166087a27d0aa7b100da563c25f7e5a52612ce50
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="72e34-102">ISymUnmanagedWriter::DefineParameter (Método)</span><span class="sxs-lookup"><span data-stu-id="72e34-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="72e34-103">Define un único parámetro del método actual.</span><span class="sxs-lookup"><span data-stu-id="72e34-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="72e34-104">El tipo de parámetro se toma de la posición del parámetro (secuencia) dentro de la firma del método.</span><span class="sxs-lookup"><span data-stu-id="72e34-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="72e34-105">Si los parámetros se definen en los metadatos de un método determinado, no tiene que volver a definirlos mediante este método.</span><span class="sxs-lookup"><span data-stu-id="72e34-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="72e34-106">Los lectores de símbolos deben comprobar los metadatos para los parámetros normales antes de comprobar el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="72e34-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72e34-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72e34-107">Syntax</span></span>  
  
```  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72e34-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72e34-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="72e34-109">[in] El nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="72e34-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="72e34-110">[in] Los atributos de parámetro.</span><span class="sxs-lookup"><span data-stu-id="72e34-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="72e34-111">[in] La firma del parámetro.</span><span class="sxs-lookup"><span data-stu-id="72e34-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="72e34-112">[in] El tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="72e34-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="72e34-113">[in] La primera dirección para la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="72e34-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="72e34-114">[in] La segunda dirección para la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="72e34-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="72e34-115">[in] La tercera dirección de la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="72e34-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72e34-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="72e34-116">Return Value</span></span>  
 <span data-ttu-id="72e34-117">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="72e34-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72e34-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72e34-118">Requirements</span></span>  
 <span data-ttu-id="72e34-119">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="72e34-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72e34-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="72e34-120">See Also</span></span>  
 [<span data-ttu-id="72e34-121">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="72e34-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
