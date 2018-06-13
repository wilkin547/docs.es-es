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
ms.openlocfilehash: 4f34f7f4ada3f8d61c9d855eab1b8b073a3d5ed8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599208"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="043fb-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="043fb-102">WriteOnly (Visual Basic)</span></span>
<span data-ttu-id="043fb-103">Especifica que se puede escribir pero no leer una propiedad.</span><span class="sxs-lookup"><span data-stu-id="043fb-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="043fb-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="043fb-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="043fb-105">Reglas</span><span class="sxs-lookup"><span data-stu-id="043fb-105">Rules</span></span>  
 <span data-ttu-id="043fb-106">**Contexto de la declaración.**</span><span class="sxs-lookup"><span data-stu-id="043fb-106">**Declaration Context.**</span></span> <span data-ttu-id="043fb-107">Solo se puede usar `WriteOnly` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="043fb-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="043fb-108">Esto significa que el contexto de la declaración de un `WriteOnly` propiedad debe ser una clase, estructura o módulo y no puede ser un archivo de código fuente, un espacio de nombres o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="043fb-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="043fb-109">Puede declarar una propiedad como `WriteOnly`, pero no una variable.</span><span class="sxs-lookup"><span data-stu-id="043fb-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="043fb-110">Cuándo se utiliza WriteOnly</span><span class="sxs-lookup"><span data-stu-id="043fb-110">When to Use WriteOnly</span></span>  
 <span data-ttu-id="043fb-111">A veces desea que el código usado para poder establecer un valor pero no descubrir lo que es.</span><span class="sxs-lookup"><span data-stu-id="043fb-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="043fb-112">Por ejemplo, los datos confidenciales, como un número de registro social o una contraseña, deben protegerse contra el acceso por cualquier componente que no haya establecido.</span><span class="sxs-lookup"><span data-stu-id="043fb-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="043fb-113">En estos casos, puede usar un `WriteOnly` propiedad para establecer el valor.</span><span class="sxs-lookup"><span data-stu-id="043fb-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="043fb-114">Al definir y utilizar un `WriteOnly` propiedad, considere la posibilidad de las medidas de protección adicionales siguientes:</span><span class="sxs-lookup"><span data-stu-id="043fb-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
-   <span data-ttu-id="043fb-115">**Reemplazar.**</span><span class="sxs-lookup"><span data-stu-id="043fb-115">**Overriding.**</span></span> <span data-ttu-id="043fb-116">Si la propiedad es un miembro de una clase, permite que de forma predeterminada [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)y no se ha declarado `Overridable` o `MustOverride`.</span><span class="sxs-lookup"><span data-stu-id="043fb-116">If the property is a member of a class, allow it to default to [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="043fb-117">Esto impide que una clase derivada que realiza el acceso no deseado a través de una invalidación.</span><span class="sxs-lookup"><span data-stu-id="043fb-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
-   <span data-ttu-id="043fb-118">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="043fb-118">**Access Level.**</span></span> <span data-ttu-id="043fb-119">Si mantiene los datos confidenciales de la propiedad en una o más variables, declárelos [privada](../../../visual-basic/language-reference/modifiers/private.md) para que ningún otro código pueda acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="043fb-119">If you hold the property's sensitive data in one or more variables, declare them [Private](../../../visual-basic/language-reference/modifiers/private.md) so that no other code can access them.</span></span>  
  
-   <span data-ttu-id="043fb-120">**Cifrado.**</span><span class="sxs-lookup"><span data-stu-id="043fb-120">**Encryption.**</span></span> <span data-ttu-id="043fb-121">Almacene todos los datos confidenciales en un formato cifrado en lugar de en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="043fb-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="043fb-122">Si algún modo, el código malintencionado obtiene acceso a dicha área de memoria, es más difícil de tomar el uso de los datos.</span><span class="sxs-lookup"><span data-stu-id="043fb-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="043fb-123">Cifrado también es útil si es necesario serializar los datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="043fb-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
-   <span data-ttu-id="043fb-124">**Restablecer.**</span><span class="sxs-lookup"><span data-stu-id="043fb-124">**Resetting.**</span></span> <span data-ttu-id="043fb-125">Cuando se termina la clase, estructura o módulo que define la propiedad, restablezca los datos sensibles a los valores predeterminados o a otros valores sin sentido.</span><span class="sxs-lookup"><span data-stu-id="043fb-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="043fb-126">Esto proporciona una protección adicional cuando esa área de memoria se libera para el acceso general.</span><span class="sxs-lookup"><span data-stu-id="043fb-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
-   <span data-ttu-id="043fb-127">**Persistencia.**</span><span class="sxs-lookup"><span data-stu-id="043fb-127">**Persistence.**</span></span> <span data-ttu-id="043fb-128">No se conservan los datos confidenciales, por ejemplo en el disco, si se pueden evitar.</span><span class="sxs-lookup"><span data-stu-id="043fb-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="043fb-129">Además, no escriba los datos confidenciales en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="043fb-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="043fb-130">El `WriteOnly` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="043fb-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="043fb-131">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="043fb-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="043fb-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="043fb-132">See Also</span></span>  
 [<span data-ttu-id="043fb-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="043fb-133">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [<span data-ttu-id="043fb-134">Private</span><span class="sxs-lookup"><span data-stu-id="043fb-134">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="043fb-135">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="043fb-135">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
