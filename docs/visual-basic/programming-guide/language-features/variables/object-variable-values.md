---
description: 'Más información sobre: valores de variables de objeto (Visual Basic)'
title: Valores de las variables de objeto
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: 3259a0b04ed629feea89c1a3e9dba69ed7d226f6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481680"
---
# <a name="object-variable-values-visual-basic"></a><span data-ttu-id="b6494-103">Valores de las variables de objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6494-103">Object Variable Values (Visual Basic)</span></span>

<span data-ttu-id="b6494-104">Una variable del [tipo de datos Object](../../../language-reference/data-types/object-data-type.md) puede hacer referencia a datos de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="b6494-104">A variable of the [Object Data Type](../../../language-reference/data-types/object-data-type.md) can refer to data of any type.</span></span> <span data-ttu-id="b6494-105">El valor que se almacena en una `Object` variable se mantiene en cualquier parte de la memoria, mientras que la propia variable contiene un puntero a los datos.</span><span class="sxs-lookup"><span data-stu-id="b6494-105">The value you store in an `Object` variable is kept elsewhere in memory, while the variable itself holds a pointer to the data.</span></span>  
  
## <a name="object-classifier-functions"></a><span data-ttu-id="b6494-106">Funciones clasificadores de objetos</span><span class="sxs-lookup"><span data-stu-id="b6494-106">Object Classifier Functions</span></span>  

 <span data-ttu-id="b6494-107">Visual Basic proporciona funciones que devuelven información sobre `Object` a qué hace referencia una variable, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b6494-107">Visual Basic supplies functions that return information about what an `Object` variable refers to, as shown in the following table.</span></span>  
  
|<span data-ttu-id="b6494-108">Función</span><span class="sxs-lookup"><span data-stu-id="b6494-108">Function</span></span>|<span data-ttu-id="b6494-109">Devuelve true si la variable de objeto hace referencia a</span><span class="sxs-lookup"><span data-stu-id="b6494-109">Returns True if the Object variable refers to</span></span>|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|<span data-ttu-id="b6494-110">Matriz de valores, en lugar de un valor único.</span><span class="sxs-lookup"><span data-stu-id="b6494-110">An array of values, rather than a single value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|<span data-ttu-id="b6494-111">Un valor de [tipo de datos de fecha](../../../language-reference/data-types/date-data-type.md) o una cadena que se puede interpretar como un valor de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="b6494-111">A [Date Data Type](../../../language-reference/data-types/date-data-type.md) value, or a string that can be interpreted as a date and time value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|<span data-ttu-id="b6494-112">Objeto de tipo <xref:System.DBNull> , que representa los datos que faltan o que no existen.</span><span class="sxs-lookup"><span data-stu-id="b6494-112">An object of type <xref:System.DBNull>, which represents missing or nonexistent data</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|<span data-ttu-id="b6494-113">Un objeto de excepción, que se deriva de <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="b6494-113">An exception object, which derives from <xref:System.Exception></span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|<span data-ttu-id="b6494-114">[Nothing](../../../language-reference/nothing.md), es decir, no hay ningún objeto asignado actualmente a la variable.</span><span class="sxs-lookup"><span data-stu-id="b6494-114">[Nothing](../../../language-reference/nothing.md), that is, no object is currently assigned to the variable</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|<span data-ttu-id="b6494-115">Un número o una cadena que se puede interpretar como un número.</span><span class="sxs-lookup"><span data-stu-id="b6494-115">A number, or a string that can be interpreted as a number</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|<span data-ttu-id="b6494-116">Un tipo de referencia (como una cadena, una matriz, un delegado o un tipo de clase)</span><span class="sxs-lookup"><span data-stu-id="b6494-116">A reference type (such as a string, array, delegate, or class type)</span></span>|  
  
 <span data-ttu-id="b6494-117">Puede utilizar estas funciones para evitar el envío de un valor no válido a una operación o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b6494-117">You can use these functions to avoid submitting an invalid value to an operation or a procedure.</span></span>  
  
## <a name="typeof-operator"></a><span data-ttu-id="b6494-118">Operador TypeOf</span><span class="sxs-lookup"><span data-stu-id="b6494-118">TypeOf Operator</span></span>  

 <span data-ttu-id="b6494-119">También puede usar el [operador typeof](../../../language-reference/operators/typeof-operator.md) para determinar si una variable de objeto hace referencia actualmente a un tipo de datos específico.</span><span class="sxs-lookup"><span data-stu-id="b6494-119">You can also use the [TypeOf Operator](../../../language-reference/operators/typeof-operator.md) to determine whether an object variable currently refers to a specific data type.</span></span> <span data-ttu-id="b6494-120">La `TypeOf` expresión... `Is` se evalúa como `True` si el tipo en tiempo de ejecución del operando se deriva del tipo especificado o lo implementa.</span><span class="sxs-lookup"><span data-stu-id="b6494-120">The `TypeOf`...`Is` expression evaluates to `True` if the run-time type of the operand is derived from or implements the specified type.</span></span>  
  
 <span data-ttu-id="b6494-121">En el ejemplo siguiente se utiliza `TypeOf` en variables de objeto que hacen referencia a tipos de valor y de referencia.</span><span class="sxs-lookup"><span data-stu-id="b6494-121">The following example uses `TypeOf` on object variables referring to value and reference types.</span></span>  
  
```vb  
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
  
 <span data-ttu-id="b6494-122">En el ejemplo anterior se escriben las líneas siguientes en la ventana de **depuración** :</span><span class="sxs-lookup"><span data-stu-id="b6494-122">The preceding example writes the following lines to the **Debug** window:</span></span>  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 <span data-ttu-id="b6494-123">La variable `num` de objeto hace referencia a los datos de tipo `Integer` y `frm` hace referencia a un objeto de clase <xref:System.Windows.Forms.Form> .</span><span class="sxs-lookup"><span data-stu-id="b6494-123">The object variable `num` refers to data of type `Integer`, and `frm` refers to an object of class <xref:System.Windows.Forms.Form>.</span></span>  
  
## <a name="object-arrays"></a><span data-ttu-id="b6494-124">Matrices de objetos</span><span class="sxs-lookup"><span data-stu-id="b6494-124">Object Arrays</span></span>  

 <span data-ttu-id="b6494-125">Puede declarar y usar una matriz de `Object` variables.</span><span class="sxs-lookup"><span data-stu-id="b6494-125">You can declare and use an array of `Object` variables.</span></span> <span data-ttu-id="b6494-126">Esto resulta útil cuando se necesita controlar una variedad de tipos de datos y clases de objetos.</span><span class="sxs-lookup"><span data-stu-id="b6494-126">This is useful when you need to handle a variety of data types and object classes.</span></span> <span data-ttu-id="b6494-127">Todos los elementos de una matriz deben tener el mismo tipo de datos declarado.</span><span class="sxs-lookup"><span data-stu-id="b6494-127">All the elements in an array must have the same declared data type.</span></span> <span data-ttu-id="b6494-128">La declaración de este tipo de datos como `Object` le permite almacenar objetos e instancias de clase junto con otros tipos de datos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b6494-128">Declaring this data type as `Object` allows you to store objects and class instances alongside other data types in the array.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6494-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6494-129">See also</span></span>

- [<span data-ttu-id="b6494-130">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="b6494-130">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="b6494-131">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="b6494-131">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="b6494-132">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="b6494-132">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="b6494-133">Procedimiento para hacer referencia a la instancia actual de un objeto</span><span class="sxs-lookup"><span data-stu-id="b6494-133">How to: Refer to the Current Instance of an Object</span></span>](how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="b6494-134">Procedimiento para determinar el tipo al que hace referencia una variable de objeto</span><span class="sxs-lookup"><span data-stu-id="b6494-134">How to: Determine What Type an Object Variable Refers To</span></span>](how-to-determine-what-type-an-object-variable-refers-to.md)
- [<span data-ttu-id="b6494-135">Procedimiento para determinar si dos objetos están relacionados</span><span class="sxs-lookup"><span data-stu-id="b6494-135">How to: Determine Whether Two Objects Are Related</span></span>](how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="b6494-136">Procedimiento para determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="b6494-136">How to: Determine Whether Two Objects Are Identical</span></span>](how-to-determine-whether-two-objects-are-identical.md)
- [<span data-ttu-id="b6494-137">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b6494-137">Data Types</span></span>](../data-types/index.md)
