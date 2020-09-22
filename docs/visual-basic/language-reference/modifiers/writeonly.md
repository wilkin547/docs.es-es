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
ms.openlocfilehash: 12a1030a423359a3e4122eea98e223a1a02f680c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867619"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="bd6f2-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd6f2-102">WriteOnly (Visual Basic)</span></span>

<span data-ttu-id="bd6f2-103">Especifica que una propiedad se puede escribir pero no leer.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd6f2-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd6f2-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="bd6f2-105">Reglas</span><span class="sxs-lookup"><span data-stu-id="bd6f2-105">Rules</span></span>  

 <span data-ttu-id="bd6f2-106">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="bd6f2-106">**Declaration Context.**</span></span> <span data-ttu-id="bd6f2-107">Solo se puede usar `WriteOnly` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="bd6f2-108">Esto significa que el contexto de la declaración de una `WriteOnly` propiedad debe ser una clase, una estructura o un módulo, y no puede ser un archivo de código fuente, un espacio de nombres o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="bd6f2-109">Puede declarar una propiedad como `WriteOnly` , pero no una variable.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="bd6f2-110">Cuándo usar WriteOnly</span><span class="sxs-lookup"><span data-stu-id="bd6f2-110">When to Use WriteOnly</span></span>  

 <span data-ttu-id="bd6f2-111">A veces, desea que el código de consumo pueda establecer un valor, pero no detectar lo que es.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="bd6f2-112">Por ejemplo, los datos confidenciales, como un número de registro social o una contraseña, deben protegerse contra el acceso de cualquier componente que no lo haya configurado.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="bd6f2-113">En estos casos, puede usar una `WriteOnly` propiedad para establecer el valor.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bd6f2-114">Al definir y usar una `WriteOnly` propiedad, tenga en cuenta las siguientes medidas de protección adicionales:</span><span class="sxs-lookup"><span data-stu-id="bd6f2-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
- <span data-ttu-id="bd6f2-115">**Invalidar.**</span><span class="sxs-lookup"><span data-stu-id="bd6f2-115">**Overriding.**</span></span> <span data-ttu-id="bd6f2-116">Si la propiedad es un miembro de una clase, permita que el valor predeterminado sea [NotOverridable](notoverridable.md)y no lo declare `Overridable` ni `MustOverride` .</span><span class="sxs-lookup"><span data-stu-id="bd6f2-116">If the property is a member of a class, allow it to default to [NotOverridable](notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="bd6f2-117">Esto evita que una clase derivada realice un acceso no deseado a través de una invalidación.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
- <span data-ttu-id="bd6f2-118">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="bd6f2-118">**Access Level.**</span></span> <span data-ttu-id="bd6f2-119">Si contiene los datos confidenciales de la propiedad en una o varias variables, declárelo [para que](private.md) ningún otro código pueda acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-119">If you hold the property's sensitive data in one or more variables, declare them [Private](private.md) so that no other code can access them.</span></span>  
  
- <span data-ttu-id="bd6f2-120">**Cifra.**</span><span class="sxs-lookup"><span data-stu-id="bd6f2-120">**Encryption.**</span></span> <span data-ttu-id="bd6f2-121">Almacene todos los datos confidenciales en formato cifrado en lugar de en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="bd6f2-122">Si el código malintencionado obtiene acceso de algún modo a esa área de memoria, es más difícil hacer uso de los datos.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="bd6f2-123">El cifrado también es útil si es necesario serializar la información confidencial.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
- <span data-ttu-id="bd6f2-124">**Restablecer.**</span><span class="sxs-lookup"><span data-stu-id="bd6f2-124">**Resetting.**</span></span> <span data-ttu-id="bd6f2-125">Cuando se termine la clase, estructura o módulo que define la propiedad, restablezca los datos confidenciales a los valores predeterminados o a otros valores sin sentido.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="bd6f2-126">Esto proporciona protección adicional cuando se libera ese área de memoria para el acceso general.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
- <span data-ttu-id="bd6f2-127">**Persistence.**</span><span class="sxs-lookup"><span data-stu-id="bd6f2-127">**Persistence.**</span></span> <span data-ttu-id="bd6f2-128">No conserve los datos confidenciales, por ejemplo, en el disco, si puede evitarlo.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="bd6f2-129">Además, no escriba datos confidenciales en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="bd6f2-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="bd6f2-130">El `WriteOnly` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="bd6f2-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="bd6f2-131">Property Statement</span><span class="sxs-lookup"><span data-stu-id="bd6f2-131">Property Statement</span></span>](../statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="bd6f2-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd6f2-132">See also</span></span>

- [<span data-ttu-id="bd6f2-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="bd6f2-133">ReadOnly</span></span>](readonly.md)
- [<span data-ttu-id="bd6f2-134">Privado</span><span class="sxs-lookup"><span data-stu-id="bd6f2-134">Private</span></span>](private.md)
- [<span data-ttu-id="bd6f2-135">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="bd6f2-135">Keywords</span></span>](../keywords/index.md)
