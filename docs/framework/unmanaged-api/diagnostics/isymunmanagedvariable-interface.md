---
description: 'Más información acerca de: interfaz ISymUnmanagedVariable'
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
ms.openlocfilehash: 15b6c7018f92ad4c82abb9e5b4e52bf428b3f54b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762700"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="65767-103">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="65767-103">ISymUnmanagedVariable Interface</span></span>

<span data-ttu-id="65767-104">Representa una variable, como un parámetro, una variable local o un campo.</span><span class="sxs-lookup"><span data-stu-id="65767-104">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65767-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="65767-105">Methods</span></span>  
  
|<span data-ttu-id="65767-106">Método</span><span class="sxs-lookup"><span data-stu-id="65767-106">Method</span></span>|<span data-ttu-id="65767-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="65767-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65767-108">Método GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="65767-108">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="65767-109">Obtiene el primer campo de dirección para esta variable.</span><span class="sxs-lookup"><span data-stu-id="65767-109">Gets the first address field for this variable.</span></span> <span data-ttu-id="65767-110">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="65767-110">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="65767-111">Método GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="65767-111">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="65767-112">Obtiene el segundo campo de dirección para esta variable.</span><span class="sxs-lookup"><span data-stu-id="65767-112">Gets the second address field for this variable.</span></span> <span data-ttu-id="65767-113">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="65767-113">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="65767-114">Método GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="65767-114">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="65767-115">Obtiene el tercer campo de dirección para esta variable.</span><span class="sxs-lookup"><span data-stu-id="65767-115">Gets the third address field for this variable.</span></span> <span data-ttu-id="65767-116">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="65767-116">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="65767-117">Método GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="65767-117">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="65767-118">Obtiene el tipo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="65767-118">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="65767-119">Método GetAttributes</span><span class="sxs-lookup"><span data-stu-id="65767-119">GetAttributes Method</span></span>](isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="65767-120">Obtiene las marcas de atributo para esta variable.</span><span class="sxs-lookup"><span data-stu-id="65767-120">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="65767-121">GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="65767-121">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="65767-122">Obtiene el desplazamiento final de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="65767-122">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="65767-123">Método GetName</span><span class="sxs-lookup"><span data-stu-id="65767-123">GetName Method</span></span>](isymunmanagedvariable-getname-method.md)|<span data-ttu-id="65767-124">Obtiene el nombre de esta variable.</span><span class="sxs-lookup"><span data-stu-id="65767-124">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="65767-125">GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="65767-125">GetSignature Method</span></span>](isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="65767-126">Obtiene la firma de esta variable.</span><span class="sxs-lookup"><span data-stu-id="65767-126">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="65767-127">Método GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="65767-127">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="65767-128">Obtiene el desplazamiento inicial de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="65767-128">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65767-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65767-129">Requirements</span></span>  

 <span data-ttu-id="65767-130">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="65767-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65767-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="65767-131">See also</span></span>

- [<span data-ttu-id="65767-132">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="65767-132">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
