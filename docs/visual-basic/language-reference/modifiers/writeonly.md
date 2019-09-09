---
title: WriteOnly (Visual Basic)
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
ms.openlocfilehash: 43507ac8e9b5843e8fa9496737a3d77b3a425a7f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963767"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="bf79b-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf79b-102">WriteOnly (Visual Basic)</span></span>
<span data-ttu-id="bf79b-103">Especifica que una propiedad se puede escribir pero no leer.</span><span class="sxs-lookup"><span data-stu-id="bf79b-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf79b-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf79b-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="bf79b-105">Reglas</span><span class="sxs-lookup"><span data-stu-id="bf79b-105">Rules</span></span>  
 <span data-ttu-id="bf79b-106">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="bf79b-106">**Declaration Context.**</span></span> <span data-ttu-id="bf79b-107">Solo se puede usar `WriteOnly` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="bf79b-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="bf79b-108">Esto significa que el contexto de la `WriteOnly` declaración de una propiedad debe ser una clase, una estructura o un módulo, y no puede ser un archivo de código fuente, un espacio de nombres o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bf79b-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="bf79b-109">Puede declarar una propiedad como `WriteOnly`, pero no una variable.</span><span class="sxs-lookup"><span data-stu-id="bf79b-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="bf79b-110">Cuándo usar WriteOnly</span><span class="sxs-lookup"><span data-stu-id="bf79b-110">When to Use WriteOnly</span></span>  
 <span data-ttu-id="bf79b-111">A veces, desea que el código de consumo pueda establecer un valor, pero no detectar lo que es.</span><span class="sxs-lookup"><span data-stu-id="bf79b-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="bf79b-112">Por ejemplo, los datos confidenciales, como un número de registro social o una contraseña, deben protegerse contra el acceso de cualquier componente que no lo haya configurado.</span><span class="sxs-lookup"><span data-stu-id="bf79b-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="bf79b-113">En estos casos, puede usar una `WriteOnly` propiedad para establecer el valor.</span><span class="sxs-lookup"><span data-stu-id="bf79b-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bf79b-114">Al definir y usar una `WriteOnly` propiedad, tenga en cuenta las siguientes medidas de protección adicionales:</span><span class="sxs-lookup"><span data-stu-id="bf79b-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
- <span data-ttu-id="bf79b-115">**Invalidar.**</span><span class="sxs-lookup"><span data-stu-id="bf79b-115">**Overriding.**</span></span> <span data-ttu-id="bf79b-116">Si la propiedad es un miembro de una clase, permita que el valor predeterminado sea [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)y no lo declare `Overridable` ni `MustOverride`.</span><span class="sxs-lookup"><span data-stu-id="bf79b-116">If the property is a member of a class, allow it to default to [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="bf79b-117">Esto evita que una clase derivada realice un acceso no deseado a través de una invalidación.</span><span class="sxs-lookup"><span data-stu-id="bf79b-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
- <span data-ttu-id="bf79b-118">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="bf79b-118">**Access Level.**</span></span> <span data-ttu-id="bf79b-119">Si contiene los datos confidenciales de la propiedad en una o varias variables, declárelo [para que](../../../visual-basic/language-reference/modifiers/private.md) ningún otro código pueda acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="bf79b-119">If you hold the property's sensitive data in one or more variables, declare them [Private](../../../visual-basic/language-reference/modifiers/private.md) so that no other code can access them.</span></span>  
  
- <span data-ttu-id="bf79b-120">**Cifra.**</span><span class="sxs-lookup"><span data-stu-id="bf79b-120">**Encryption.**</span></span> <span data-ttu-id="bf79b-121">Almacene todos los datos confidenciales en formato cifrado en lugar de en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="bf79b-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="bf79b-122">Si el código malintencionado obtiene acceso de algún modo a esa área de memoria, es más difícil hacer uso de los datos.</span><span class="sxs-lookup"><span data-stu-id="bf79b-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="bf79b-123">El cifrado también es útil si es necesario serializar la información confidencial.</span><span class="sxs-lookup"><span data-stu-id="bf79b-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
- <span data-ttu-id="bf79b-124">**Restablecer.**</span><span class="sxs-lookup"><span data-stu-id="bf79b-124">**Resetting.**</span></span> <span data-ttu-id="bf79b-125">Cuando se termine la clase, estructura o módulo que define la propiedad, restablezca los datos confidenciales a los valores predeterminados o a otros valores sin sentido.</span><span class="sxs-lookup"><span data-stu-id="bf79b-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="bf79b-126">Esto proporciona protección adicional cuando se libera ese área de memoria para el acceso general.</span><span class="sxs-lookup"><span data-stu-id="bf79b-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
- <span data-ttu-id="bf79b-127">**Persistence.**</span><span class="sxs-lookup"><span data-stu-id="bf79b-127">**Persistence.**</span></span> <span data-ttu-id="bf79b-128">No conserve los datos confidenciales, por ejemplo, en el disco, si puede evitarlo.</span><span class="sxs-lookup"><span data-stu-id="bf79b-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="bf79b-129">Además, no escriba datos confidenciales en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="bf79b-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="bf79b-130">El `WriteOnly` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="bf79b-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="bf79b-131">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bf79b-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="bf79b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf79b-132">See also</span></span>

- [<span data-ttu-id="bf79b-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="bf79b-133">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="bf79b-134">Private</span><span class="sxs-lookup"><span data-stu-id="bf79b-134">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="bf79b-135">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="bf79b-135">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
