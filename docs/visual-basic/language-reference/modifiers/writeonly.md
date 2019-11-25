---
title: WriteOnly
ms.date: 07/20/2015
f1_keywords:
- WriteOnly
- vb.WriteOnly
helpviewer_keywords:
- write-only properties
- WriteOnly keyword [Visual Basic]
- sensitive data, protecting
- properties [Visual Basic], write-only
- sensitive data
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
ms.openlocfilehash: 847617ea6534089857a759fbea3bb16a3a5a36a1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344192"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="3ee66-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ee66-102">WriteOnly (Visual Basic)</span></span>
<span data-ttu-id="3ee66-103">Specifies that a property can be written but not read.</span><span class="sxs-lookup"><span data-stu-id="3ee66-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ee66-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ee66-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="3ee66-105">Reglas</span><span class="sxs-lookup"><span data-stu-id="3ee66-105">Rules</span></span>  
 <span data-ttu-id="3ee66-106">**Declaration Context.**</span><span class="sxs-lookup"><span data-stu-id="3ee66-106">**Declaration Context.**</span></span> <span data-ttu-id="3ee66-107">Solo se puede usar `WriteOnly` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="3ee66-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="3ee66-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span><span class="sxs-lookup"><span data-stu-id="3ee66-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="3ee66-109">You can declare a property as `WriteOnly`, but not a variable.</span><span class="sxs-lookup"><span data-stu-id="3ee66-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="3ee66-110">When to Use WriteOnly</span><span class="sxs-lookup"><span data-stu-id="3ee66-110">When to Use WriteOnly</span></span>  
 <span data-ttu-id="3ee66-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span><span class="sxs-lookup"><span data-stu-id="3ee66-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="3ee66-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span><span class="sxs-lookup"><span data-stu-id="3ee66-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="3ee66-113">In these cases, you can use a `WriteOnly` property to set the value.</span><span class="sxs-lookup"><span data-stu-id="3ee66-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3ee66-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span><span class="sxs-lookup"><span data-stu-id="3ee66-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
- <span data-ttu-id="3ee66-115">**Overriding.**</span><span class="sxs-lookup"><span data-stu-id="3ee66-115">**Overriding.**</span></span> <span data-ttu-id="3ee66-116">If the property is a member of a class, allow it to default to [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span><span class="sxs-lookup"><span data-stu-id="3ee66-116">If the property is a member of a class, allow it to default to [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="3ee66-117">This prevents a derived class from making undesired access through an override.</span><span class="sxs-lookup"><span data-stu-id="3ee66-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
- <span data-ttu-id="3ee66-118">**Access Level.**</span><span class="sxs-lookup"><span data-stu-id="3ee66-118">**Access Level.**</span></span> <span data-ttu-id="3ee66-119">If you hold the property's sensitive data in one or more variables, declare them [Private](../../../visual-basic/language-reference/modifiers/private.md) so that no other code can access them.</span><span class="sxs-lookup"><span data-stu-id="3ee66-119">If you hold the property's sensitive data in one or more variables, declare them [Private](../../../visual-basic/language-reference/modifiers/private.md) so that no other code can access them.</span></span>  
  
- <span data-ttu-id="3ee66-120">**Encryption.**</span><span class="sxs-lookup"><span data-stu-id="3ee66-120">**Encryption.**</span></span> <span data-ttu-id="3ee66-121">Store all sensitive data in encrypted form rather than in plain text.</span><span class="sxs-lookup"><span data-stu-id="3ee66-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="3ee66-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span><span class="sxs-lookup"><span data-stu-id="3ee66-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="3ee66-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span><span class="sxs-lookup"><span data-stu-id="3ee66-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
- <span data-ttu-id="3ee66-124">**Resetting.**</span><span class="sxs-lookup"><span data-stu-id="3ee66-124">**Resetting.**</span></span> <span data-ttu-id="3ee66-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span><span class="sxs-lookup"><span data-stu-id="3ee66-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="3ee66-126">This gives extra protection when that area of memory is freed for general access.</span><span class="sxs-lookup"><span data-stu-id="3ee66-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
- <span data-ttu-id="3ee66-127">**Persistence.**</span><span class="sxs-lookup"><span data-stu-id="3ee66-127">**Persistence.**</span></span> <span data-ttu-id="3ee66-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span><span class="sxs-lookup"><span data-stu-id="3ee66-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="3ee66-129">Also, do not write any sensitive data to the Clipboard.</span><span class="sxs-lookup"><span data-stu-id="3ee66-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="3ee66-130">The `WriteOnly` modifier can be used in this context:</span><span class="sxs-lookup"><span data-stu-id="3ee66-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="3ee66-131">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3ee66-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3ee66-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ee66-132">See also</span></span>

- [<span data-ttu-id="3ee66-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="3ee66-133">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="3ee66-134">Private</span><span class="sxs-lookup"><span data-stu-id="3ee66-134">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="3ee66-135">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3ee66-135">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
