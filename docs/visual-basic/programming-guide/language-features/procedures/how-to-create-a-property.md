---
title: "Cómo: Crear una propiedad (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d140e6a10061f7fabe3d12c6cce5d0c201e103d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-property-visual-basic"></a><span data-ttu-id="9befb-102">Cómo: Crear una propiedad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9befb-102">How to: Create a Property (Visual Basic)</span></span>
<span data-ttu-id="9befb-103">Incluir una definición de propiedad entre un `Property` instrucción y un `End Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="9befb-103">You enclose a property definition between a `Property` statement and an `End Property` statement.</span></span> <span data-ttu-id="9befb-104">Dentro de esta definición se define un `Get` procedimiento, un `Set` procedimiento, o ambos.</span><span class="sxs-lookup"><span data-stu-id="9befb-104">Within this definition you define a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="9befb-105">Código de la de la propiedad se encuentra dentro de estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="9befb-105">All the property's code lies within these procedures.</span></span>  
  
 <span data-ttu-id="9befb-106">El `Get` procedimiento recupera el valor de la propiedad y el `Set` procedimiento almacena un valor.</span><span class="sxs-lookup"><span data-stu-id="9befb-106">The `Get` procedure retrieves the property's value, and the `Set` procedure stores a value.</span></span> <span data-ttu-id="9befb-107">Si desea que la propiedad que se va a tener acceso de lectura/escritura, debe definir ambos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="9befb-107">If you want the property to have read/write access, you must define both procedures.</span></span> <span data-ttu-id="9befb-108">Para una propiedad de solo lectura, definir solo `Get`, y para una propiedad de solo escritura, definir solo `Set`.</span><span class="sxs-lookup"><span data-stu-id="9befb-108">For a read-only property, you define only `Get`, and for a write-only property, you define only `Set`.</span></span>  
  
### <a name="to-create-a-property"></a><span data-ttu-id="9befb-109">Para crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="9befb-109">To create a property</span></span>  
  
1.  <span data-ttu-id="9befb-110">Fuera de cualquier propiedad o procedimiento, utilice un [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md), seguido de un `End Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="9befb-110">Outside any property or procedure, use a [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md), followed by an `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="9befb-111">Si la propiedad toma parámetros, siga el `Property` palabra clave con el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="9befb-111">If the property takes parameters, follow the `Property` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="9befb-112">Siga los paréntesis con un `As` cláusula para especificar el tipo de datos del valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9befb-112">Follow the parentheses with an `As` clause to specify the data type of the property's value.</span></span> <span data-ttu-id="9befb-113">Debe especificar el tipo de datos incluso para una propiedad de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="9befb-113">You must specify the data type even for a write-only property.</span></span>  
  
4.  <span data-ttu-id="9befb-114">Agregar `Get` y `Set` procedimientos, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="9befb-114">Add `Get` and `Set` procedures, as appropriate.</span></span> <span data-ttu-id="9befb-115">Vea las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="9befb-115">See the following directions.</span></span>  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a><span data-ttu-id="9befb-116">Para crear un procedimiento Get que recupera un valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="9befb-116">To create a Get procedure that retrieves a property value</span></span>  
  
1.  <span data-ttu-id="9befb-117">Entre los `Property` y `End Property` instrucciones, escribir una [instrucción Get](../../../../visual-basic/language-reference/statements/get-statement.md), seguido de un `End Get` instrucción.</span><span class="sxs-lookup"><span data-stu-id="9befb-117">Between the `Property` and `End Property` statements, write a [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md), followed by an `End Get` statement.</span></span> <span data-ttu-id="9befb-118">No es necesario definir los parámetros para el `Get` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9befb-118">You do not need to define any parameters for the `Get` procedure.</span></span>  
  
2.  <span data-ttu-id="9befb-119">Coloque las instrucciones de código para recuperar el valor de propiedad entre el `Get` y `End Get` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="9befb-119">Place the code statements to retrieve the property's value between the `Get` and `End Get` statements.</span></span> <span data-ttu-id="9befb-120">Este código puede incluir otros cálculos y manipulaciones de datos además de generar y devolver el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9befb-120">This code can include other calculations and data manipulations in addition to generating and returning the property's value.</span></span>  
  
3.  <span data-ttu-id="9befb-121">Use un `Return` instrucción para devolver el valor de propiedad para el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="9befb-121">Use a `Return` statement to return the property's value to the calling code.</span></span>  
  
 <span data-ttu-id="9befb-122">Debe escribir un `Get` procedimiento para una propiedad de lectura y escritura así como para una propiedad de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="9befb-122">You must write a `Get` procedure for a read-write property and for a read-only property.</span></span> <span data-ttu-id="9befb-123">No debe definir un `Get` procedimiento para una propiedad de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="9befb-123">You must not define a `Get` procedure for a write-only property.</span></span>  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a><span data-ttu-id="9befb-124">Para crear un procedimiento Set que escribe el valor de la propiedad</span><span class="sxs-lookup"><span data-stu-id="9befb-124">To create a Set procedure that writes a property's value</span></span>  
  
1.  <span data-ttu-id="9befb-125">Entre los `Property` y `End Property` instrucciones, escribir una [instrucción Set](../../../../visual-basic/language-reference/statements/set-statement.md), seguido de un `End Set` instrucción.</span><span class="sxs-lookup"><span data-stu-id="9befb-125">Between the `Property` and `End Property` statements, write a [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md), followed by an `End Set` statement.</span></span>  
  
2.  <span data-ttu-id="9befb-126">En el `Set` (instrucción), siga el `Set` palabra clave con una lista de parámetros entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="9befb-126">In the `Set` statement, follow the `Set` keyword with a parameter list in parentheses.</span></span> <span data-ttu-id="9befb-127">Esta lista de parámetros debe incluir al menos un parámetro de valor para el valor pasado por el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="9befb-127">This parameter list must include at least a value parameter for the value passed by the calling code.</span></span> <span data-ttu-id="9befb-128">El nombre predeterminado para este parámetro de valor es `Value`, pero puede utilizar un nombre diferente según corresponda.</span><span class="sxs-lookup"><span data-stu-id="9befb-128">The default name for this value parameter is `Value`, but you can use a different name if appropriate.</span></span> <span data-ttu-id="9befb-129">El valor del parámetro debe tener los mismos datos de tipo que la propiedad en Sí.</span><span class="sxs-lookup"><span data-stu-id="9befb-129">The value parameter must have the same data type as the property itself.</span></span>  
  
3.  <span data-ttu-id="9befb-130">Coloque las instrucciones de código para almacenar un valor en la propiedad entre el `Set` y `End Set` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="9befb-130">Place the code statements to store a value in the property between the `Set` and `End Set` statements.</span></span> <span data-ttu-id="9befb-131">Este código puede incluir otros cálculos y manipulaciones de datos además de validar y almacenar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9befb-131">This code can include other calculations and data manipulations in addition to validating and storing the property's value.</span></span>  
  
4.  <span data-ttu-id="9befb-132">Use el valor del parámetro para aceptar el valor proporcionado por el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="9befb-132">Use the value parameter to accept the value supplied by the calling code.</span></span> <span data-ttu-id="9befb-133">Puede almacenar este valor directamente en una instrucción de asignación o utilizarlo en una expresión para calcular el valor interno que se almacenará.</span><span class="sxs-lookup"><span data-stu-id="9befb-133">You can either store this value directly in an assignment statement, or use it in an expression to calculate the internal value to be stored.</span></span>  
  
 <span data-ttu-id="9befb-134">Debe escribir un `Set` procedimiento para una propiedad de lectura y escritura así como para una propiedad de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="9befb-134">You must write a `Set` procedure for a read-write property and for a write-only property.</span></span> <span data-ttu-id="9befb-135">No debe definir un `Set` procedimiento para una propiedad de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="9befb-135">You must not define a `Set` procedure for a read-only property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9befb-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9befb-136">Example</span></span>  
 <span data-ttu-id="9befb-137">En el ejemplo siguiente se crea una propiedad de lectura/escritura que almacena un nombre completo como dos nombres que lo componen, el nombre y el apellido.</span><span class="sxs-lookup"><span data-stu-id="9befb-137">The following example creates a read/write property that stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="9befb-138">Cuando se lee el código de llamada `fullName`, el `Get` procedimiento combina los dos nombres constituyentes y devuelve el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="9befb-138">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="9befb-139">Cuando el código de llamada asigna un nuevo nombre completo, el `Set` procedimiento intenta dividir en dos nombres que lo componen.</span><span class="sxs-lookup"><span data-stu-id="9befb-139">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="9befb-140">Si no encuentra un espacio, lo almacena todos como el nombre.</span><span class="sxs-lookup"><span data-stu-id="9befb-140">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/how-to-create-a-property_1.vb)]  
  
 <span data-ttu-id="9befb-141">El ejemplo siguiente muestra las llamadas típicas a los procedimientos de propiedad de `fullName`.</span><span class="sxs-lookup"><span data-stu-id="9befb-141">The following example shows typical calls to the property procedures of `fullName`.</span></span> <span data-ttu-id="9befb-142">La primera llamada establece el valor de propiedad y la segunda llamada lo recupera.</span><span class="sxs-lookup"><span data-stu-id="9befb-142">The first call sets the property value and the second call retrieves it.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/how-to-create-a-property_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9befb-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="9befb-143">See Also</span></span>  
 [<span data-ttu-id="9befb-144">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="9befb-144">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="9befb-145">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="9befb-145">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="9befb-146">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="9befb-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="9befb-147">Diferencias entre propiedades y Variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9befb-147">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="9befb-148">Declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="9befb-148">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="9befb-149">Llamar a un procedimiento de propiedad</span><span class="sxs-lookup"><span data-stu-id="9befb-149">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="9befb-150">Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9befb-150">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="9befb-151">Establecer un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="9befb-151">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="9befb-152">Obtener un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="9befb-152">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
