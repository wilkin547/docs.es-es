---
title: ISymUnmanagedVariable (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 712eca7f3f9fec9c81e638802f5a664ec6469d53
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164351"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="d4bbd-102">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4bbd-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="d4bbd-103">Representa una variable, como un parámetro, una variable local o un campo.</span><span class="sxs-lookup"><span data-stu-id="d4bbd-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d4bbd-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d4bbd-104">Methods</span></span>  
  
|<span data-ttu-id="d4bbd-105">Método</span><span class="sxs-lookup"><span data-stu-id="d4bbd-105">Method</span></span>|<span data-ttu-id="d4bbd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4bbd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d4bbd-107">GetAddressField1 (método)</span><span class="sxs-lookup"><span data-stu-id="d4bbd-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="d4bbd-108">Obtiene el primer campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="d4bbd-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="d4bbd-109">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="d4bbd-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="d4bbd-110">GetAddressField2 (método)</span><span class="sxs-lookup"><span data-stu-id="d4bbd-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="d4bbd-111">Obtiene el segundo campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="d4bbd-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="d4bbd-112">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="d4bbd-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="d4bbd-113">GetAddressField3 (método)</span><span class="sxs-lookup"><span data-stu-id="d4bbd-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="d4bbd-114">Obtiene el tercer campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="d4bbd-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="d4bbd-115">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="d4bbd-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="d4bbd-116">GetAddressKind (método)</span><span class="sxs-lookup"><span data-stu-id="d4bbd-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="d4bbd-117">Obtiene el tipo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="d4bbd-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="d4bbd-118">GetAttributes (método)</span><span class="sxs-lookup"><span data-stu-id="d4bbd-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="d4bbd-119">Obtiene los marcadores de atributo para esta variable.</span><span class="sxs-lookup"><span data-stu-id="d4bbd-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="d4bbd-120">GetEndOffset (método)</span><span class="sxs-lookup"><span data-stu-id="d4bbd-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="d4bbd-121">Obtiene el desplazamiento final de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="d4bbd-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="d4bbd-122">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="d4bbd-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="d4bbd-123">Obtiene el nombre de esta variable.</span><span class="sxs-lookup"><span data-stu-id="d4bbd-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="d4bbd-124">GetSignature (método)</span><span class="sxs-lookup"><span data-stu-id="d4bbd-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="d4bbd-125">Obtiene la firma de esta variable.</span><span class="sxs-lookup"><span data-stu-id="d4bbd-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="d4bbd-126">GetStartOffset (método)</span><span class="sxs-lookup"><span data-stu-id="d4bbd-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="d4bbd-127">Obtiene el desplazamiento inicial de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="d4bbd-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4bbd-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4bbd-128">Requirements</span></span>  
 <span data-ttu-id="d4bbd-129">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d4bbd-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4bbd-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4bbd-130">See also</span></span>

- [<span data-ttu-id="d4bbd-131">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="d4bbd-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
