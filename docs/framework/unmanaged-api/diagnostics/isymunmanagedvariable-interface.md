---
title: ISymUnmanagedVariable (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e5ae8d1d05274363dc523c1a2cebf4ed09c1f461
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="948d8-102">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="948d8-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="948d8-103">Representa una variable, como un parámetro, una variable local o un campo.</span><span class="sxs-lookup"><span data-stu-id="948d8-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="948d8-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="948d8-104">Methods</span></span>  
  
|<span data-ttu-id="948d8-105">Método</span><span class="sxs-lookup"><span data-stu-id="948d8-105">Method</span></span>|<span data-ttu-id="948d8-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="948d8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="948d8-107">GetAddressField1 (método)</span><span class="sxs-lookup"><span data-stu-id="948d8-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="948d8-108">Obtiene el primer campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="948d8-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="948d8-109">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="948d8-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="948d8-110">GetAddressField2 (método)</span><span class="sxs-lookup"><span data-stu-id="948d8-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="948d8-111">Obtiene el segundo campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="948d8-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="948d8-112">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="948d8-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="948d8-113">GetAddressField3 (método)</span><span class="sxs-lookup"><span data-stu-id="948d8-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="948d8-114">Obtiene el tercer campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="948d8-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="948d8-115">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="948d8-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="948d8-116">GetAddressKind (método)</span><span class="sxs-lookup"><span data-stu-id="948d8-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="948d8-117">Obtiene el tipo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="948d8-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="948d8-118">GetAttributes (método)</span><span class="sxs-lookup"><span data-stu-id="948d8-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="948d8-119">Obtiene los marcadores de atributo para esta variable.</span><span class="sxs-lookup"><span data-stu-id="948d8-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="948d8-120">GetEndOffset (método)</span><span class="sxs-lookup"><span data-stu-id="948d8-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="948d8-121">Obtiene el desplazamiento final de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="948d8-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="948d8-122">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="948d8-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="948d8-123">Obtiene el nombre de esta variable.</span><span class="sxs-lookup"><span data-stu-id="948d8-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="948d8-124">GetSignature (método)</span><span class="sxs-lookup"><span data-stu-id="948d8-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="948d8-125">Obtiene la firma de esta variable.</span><span class="sxs-lookup"><span data-stu-id="948d8-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="948d8-126">GetStartOffset (método)</span><span class="sxs-lookup"><span data-stu-id="948d8-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="948d8-127">Obtiene el desplazamiento inicial de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="948d8-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="948d8-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="948d8-128">Requirements</span></span>  
 <span data-ttu-id="948d8-129">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="948d8-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="948d8-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="948d8-130">See Also</span></span>  
 [<span data-ttu-id="948d8-131">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="948d8-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
