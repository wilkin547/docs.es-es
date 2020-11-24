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
ms.openlocfilehash: c5e36443295395997303cb94202f534a83d086f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677874"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="dd74d-102">ISymUnmanagedWriter::DefineParameter (Método)</span><span class="sxs-lookup"><span data-stu-id="dd74d-102">ISymUnmanagedWriter::DefineParameter Method</span></span>

<span data-ttu-id="dd74d-103">Define un único parámetro en el método actual.</span><span class="sxs-lookup"><span data-stu-id="dd74d-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="dd74d-104">El tipo de parámetro se toma de la posición del parámetro (Sequence) dentro de la Signatura del método.</span><span class="sxs-lookup"><span data-stu-id="dd74d-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="dd74d-105">Si los parámetros se definen en los metadatos de un método determinado, no es necesario volver a definirlos mediante este método.</span><span class="sxs-lookup"><span data-stu-id="dd74d-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="dd74d-106">Los lectores de símbolos deben comprobar los metadatos normales de los parámetros antes de comprobar el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="dd74d-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd74d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd74d-107">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="dd74d-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dd74d-108">Parameters</span></span>  

 `name`  
 <span data-ttu-id="dd74d-109">de Nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd74d-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="dd74d-110">de Atributos de parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd74d-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="dd74d-111">de Firma del parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd74d-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="dd74d-112">de Tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="dd74d-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="dd74d-113">de Primera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd74d-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="dd74d-114">de Segunda dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd74d-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="dd74d-115">de Tercera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd74d-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd74d-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dd74d-116">Return Value</span></span>  

 <span data-ttu-id="dd74d-117">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="dd74d-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd74d-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd74d-118">Requirements</span></span>  

 <span data-ttu-id="dd74d-119">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="dd74d-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd74d-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd74d-120">See also</span></span>

- [<span data-ttu-id="dd74d-121">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd74d-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
