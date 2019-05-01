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
ms.openlocfilehash: 1b8de27e872914ba59d73126d2a9a7c42609165e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051824"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="b28ca-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b28ca-102">WriteOnly (Visual Basic)</span></span>
<span data-ttu-id="b28ca-103">Especifica que se puede escribir pero no leer una propiedad.</span><span class="sxs-lookup"><span data-stu-id="b28ca-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b28ca-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b28ca-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b28ca-105">Reglas</span><span class="sxs-lookup"><span data-stu-id="b28ca-105">Rules</span></span>  
 <span data-ttu-id="b28ca-106">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="b28ca-106">**Declaration Context.**</span></span> <span data-ttu-id="b28ca-107">Solo se puede usar `WriteOnly` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="b28ca-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="b28ca-108">Esto significa que el contexto de declaración de un `WriteOnly` propiedad debe ser una clase, estructura o módulo y no puede ser un archivo de código fuente, el espacio de nombres o el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b28ca-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="b28ca-109">Puede declarar una propiedad como `WriteOnly`, pero no una variable.</span><span class="sxs-lookup"><span data-stu-id="b28ca-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="b28ca-110">Cuándo usar WriteOnly</span><span class="sxs-lookup"><span data-stu-id="b28ca-110">When to Use WriteOnly</span></span>  
 <span data-ttu-id="b28ca-111">A veces desea que el código usado para poder establecer un valor pero no descubrir lo que es.</span><span class="sxs-lookup"><span data-stu-id="b28ca-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="b28ca-112">Por ejemplo, datos confidenciales, como un número de registro de redes sociales o una contraseña, deben protegerse contra el acceso por cualquier componente que no se ha establecido.</span><span class="sxs-lookup"><span data-stu-id="b28ca-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="b28ca-113">En estos casos, puede usar un `WriteOnly` propiedad para establecer el valor.</span><span class="sxs-lookup"><span data-stu-id="b28ca-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b28ca-114">Al definir y usar un `WriteOnly` propiedad, considere la posibilidad de las medidas de protección adicionales siguientes:</span><span class="sxs-lookup"><span data-stu-id="b28ca-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
- <span data-ttu-id="b28ca-115">**Se ha invalidado.**</span><span class="sxs-lookup"><span data-stu-id="b28ca-115">**Overriding.**</span></span> <span data-ttu-id="b28ca-116">Si la propiedad es un miembro de una clase, permite que de forma predeterminada [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)y no se ha declarado `Overridable` o `MustOverride`.</span><span class="sxs-lookup"><span data-stu-id="b28ca-116">If the property is a member of a class, allow it to default to [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="b28ca-117">Esto impide que una clase derivada lo que el acceso no deseado a través de una invalidación.</span><span class="sxs-lookup"><span data-stu-id="b28ca-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
- <span data-ttu-id="b28ca-118">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="b28ca-118">**Access Level.**</span></span> <span data-ttu-id="b28ca-119">Si mantiene los datos confidenciales de la propiedad en una o más variables, declárelos [privada](../../../visual-basic/language-reference/modifiers/private.md) para que ningún otro código puede tener acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="b28ca-119">If you hold the property's sensitive data in one or more variables, declare them [Private](../../../visual-basic/language-reference/modifiers/private.md) so that no other code can access them.</span></span>  
  
- <span data-ttu-id="b28ca-120">**Cifrado.**</span><span class="sxs-lookup"><span data-stu-id="b28ca-120">**Encryption.**</span></span> <span data-ttu-id="b28ca-121">Store todos los datos confidenciales en un formato cifrado en lugar de en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="b28ca-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="b28ca-122">Si algún modo, código malintencionado obtiene acceso a esa área de memoria, es más difícil de hacer uso de los datos.</span><span class="sxs-lookup"><span data-stu-id="b28ca-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="b28ca-123">Cifrado también es útil si es necesario serializar los datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="b28ca-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
- <span data-ttu-id="b28ca-124">**Restablecer.**</span><span class="sxs-lookup"><span data-stu-id="b28ca-124">**Resetting.**</span></span> <span data-ttu-id="b28ca-125">Cuando se termina la clase, estructura o módulo que define la propiedad, restablecer la información confidencial a los valores predeterminados o a otros valores sin sentido.</span><span class="sxs-lookup"><span data-stu-id="b28ca-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="b28ca-126">Esto proporciona protección adicional cuando se libera esa área de memoria para el acceso general.</span><span class="sxs-lookup"><span data-stu-id="b28ca-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
- <span data-ttu-id="b28ca-127">**Persistencia.**</span><span class="sxs-lookup"><span data-stu-id="b28ca-127">**Persistence.**</span></span> <span data-ttu-id="b28ca-128">No se conservan los datos confidenciales, por ejemplo en el disco, si se puede evitar.</span><span class="sxs-lookup"><span data-stu-id="b28ca-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="b28ca-129">Además, no escribir los datos confidenciales en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="b28ca-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="b28ca-130">El `WriteOnly` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="b28ca-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="b28ca-131">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b28ca-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="b28ca-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b28ca-132">See also</span></span>

- [<span data-ttu-id="b28ca-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="b28ca-133">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="b28ca-134">Private</span><span class="sxs-lookup"><span data-stu-id="b28ca-134">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="b28ca-135">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b28ca-135">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
