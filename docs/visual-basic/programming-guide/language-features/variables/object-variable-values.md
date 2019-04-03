---
title: Valores de las variables de objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: c17c5f85952596f0a080ca473e8f792740e66b8f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840398"
---
# <a name="object-variable-values-visual-basic"></a><span data-ttu-id="1feb8-102">Valores de las variables de objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1feb8-102">Object Variable Values (Visual Basic)</span></span>
<span data-ttu-id="1feb8-103">Una variable de la [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) puede hacer referencia a datos de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="1feb8-103">A variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) can refer to data of any type.</span></span> <span data-ttu-id="1feb8-104">El valor que se almacena en un `Object` variable se mantiene en otro lugar en la memoria, mientras que la propia variable contiene un puntero a los datos.</span><span class="sxs-lookup"><span data-stu-id="1feb8-104">The value you store in an `Object` variable is kept elsewhere in memory, while the variable itself holds a pointer to the data.</span></span>  
  
## <a name="object-classifier-functions"></a><span data-ttu-id="1feb8-105">Funciones del objeto clasificador</span><span class="sxs-lookup"><span data-stu-id="1feb8-105">Object Classifier Functions</span></span>  
 <span data-ttu-id="1feb8-106">Visual Basic proporciona funciones que devuelven información acerca de lo que un `Object` variable hace referencia a, tal como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1feb8-106">Visual Basic supplies functions that return information about what an `Object` variable refers to, as shown in the following table.</span></span>  
  
|<span data-ttu-id="1feb8-107">Función</span><span class="sxs-lookup"><span data-stu-id="1feb8-107">Function</span></span>|<span data-ttu-id="1feb8-108">Devuelve True si la variable de objeto hace referencia a</span><span class="sxs-lookup"><span data-stu-id="1feb8-108">Returns True if the Object variable refers to</span></span>|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|<span data-ttu-id="1feb8-109">Una matriz de valores, en lugar de un solo valor</span><span class="sxs-lookup"><span data-stu-id="1feb8-109">An array of values, rather than a single value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|<span data-ttu-id="1feb8-110">Un [tipo de datos Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) valor o una cadena que se puede interpretar como un valor de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="1feb8-110">A [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) value, or a string that can be interpreted as a date and time value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|<span data-ttu-id="1feb8-111">Un objeto de tipo <xref:System.DBNull>, que representa los datos que faltan o que no existentes</span><span class="sxs-lookup"><span data-stu-id="1feb8-111">An object of type <xref:System.DBNull>, which represents missing or nonexistent data</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|<span data-ttu-id="1feb8-112">Un objeto de excepción que se deriva de <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="1feb8-112">An exception object, which derives from <xref:System.Exception></span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|<span data-ttu-id="1feb8-113">[No hay nada](../../../../visual-basic/language-reference/nothing.md), es decir, no hay ningún objeto está asignado actualmente a la variable</span><span class="sxs-lookup"><span data-stu-id="1feb8-113">[Nothing](../../../../visual-basic/language-reference/nothing.md), that is, no object is currently assigned to the variable</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|<span data-ttu-id="1feb8-114">Un número o una cadena que se puede interpretar como un número</span><span class="sxs-lookup"><span data-stu-id="1feb8-114">A number, or a string that can be interpreted as a number</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|<span data-ttu-id="1feb8-115">Un tipo de referencia (por ejemplo, una cadena, matriz, delegado o tipo de clase)</span><span class="sxs-lookup"><span data-stu-id="1feb8-115">A reference type (such as a string, array, delegate, or class type)</span></span>|  
  
 <span data-ttu-id="1feb8-116">Puede usar estas funciones para evitar el envío de un valor no válido a una operación o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1feb8-116">You can use these functions to avoid submitting an invalid value to an operation or a procedure.</span></span>  
  
## <a name="typeof-operator"></a><span data-ttu-id="1feb8-117">Operador TypeOf</span><span class="sxs-lookup"><span data-stu-id="1feb8-117">TypeOf Operator</span></span>  
 <span data-ttu-id="1feb8-118">También puede usar el [operador TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) para determinar si una variable de objeto hace referencia actualmente a un tipo de datos específico.</span><span class="sxs-lookup"><span data-stu-id="1feb8-118">You can also use the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to determine whether an object variable currently refers to a specific data type.</span></span> <span data-ttu-id="1feb8-119">El `TypeOf`... `Is` expresión se evalúa como `True` si el tipo de tiempo de ejecución del operando se deriva de o implementa el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="1feb8-119">The `TypeOf`...`Is` expression evaluates to `True` if the run-time type of the operand is derived from or implements the specified type.</span></span>  
  
 <span data-ttu-id="1feb8-120">En el ejemplo siguiente se usa `TypeOf` en variables de objeto que hace referencia a tipos de valor y de referencia.</span><span class="sxs-lookup"><span data-stu-id="1feb8-120">The following example uses `TypeOf` on object variables referring to value and reference types.</span></span>  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 <span data-ttu-id="1feb8-121">El ejemplo anterior escribe las líneas siguientes a la **depurar** ventana:</span><span class="sxs-lookup"><span data-stu-id="1feb8-121">The preceding example writes the following lines to the **Debug** window:</span></span>  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 <span data-ttu-id="1feb8-122">La variable de objeto `num` hace referencia a datos de tipo `Integer`, y `frm` hace referencia a un objeto de clase <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="1feb8-122">The object variable `num` refers to data of type `Integer`, and `frm` refers to an object of class <xref:System.Windows.Forms.Form>.</span></span>  
  
## <a name="object-arrays"></a><span data-ttu-id="1feb8-123">Matrices de objetos</span><span class="sxs-lookup"><span data-stu-id="1feb8-123">Object Arrays</span></span>  
 <span data-ttu-id="1feb8-124">Puede declarar y usar una matriz de `Object` variables.</span><span class="sxs-lookup"><span data-stu-id="1feb8-124">You can declare and use an array of `Object` variables.</span></span> <span data-ttu-id="1feb8-125">Esto es útil cuando deba controlar una variedad de tipos de datos y las clases de objeto.</span><span class="sxs-lookup"><span data-stu-id="1feb8-125">This is useful when you need to handle a variety of data types and object classes.</span></span> <span data-ttu-id="1feb8-126">Todos los elementos de matriz deben tener los mismos datos declarados de tipo.</span><span class="sxs-lookup"><span data-stu-id="1feb8-126">All the elements in an array must have the same declared data type.</span></span> <span data-ttu-id="1feb8-127">Este tipo de datos como se declara `Object` le permite almacenar objetos e instancias junto con otros tipos de datos de la matriz de clase.</span><span class="sxs-lookup"><span data-stu-id="1feb8-127">Declaring this data type as `Object` allows you to store objects and class instances alongside other data types in the array.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1feb8-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="1feb8-128">See also</span></span>

- [<span data-ttu-id="1feb8-129">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="1feb8-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="1feb8-130">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="1feb8-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="1feb8-131">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="1feb8-131">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="1feb8-132">Cómo: Hacer referencia a la instancia actual de un objeto</span><span class="sxs-lookup"><span data-stu-id="1feb8-132">How to: Refer to the Current Instance of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="1feb8-133">Cómo: Determinar qué tipo de una Variable de objeto hace referencia a</span><span class="sxs-lookup"><span data-stu-id="1feb8-133">How to: Determine What Type an Object Variable Refers To</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)
- [<span data-ttu-id="1feb8-134">Cómo: Determinar si dos objetos están relacionados</span><span class="sxs-lookup"><span data-stu-id="1feb8-134">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="1feb8-135">Cómo: Determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="1feb8-135">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
- [<span data-ttu-id="1feb8-136">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="1feb8-136">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
