---
description: 'Más información sobre: tipos de datos varios (Visual Basic)'
title: Tipos de datos varios
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: 3875a3fc3027d573013470cb96c9482a0be6cbbf
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462001"
---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="06550-103">Tipos de datos variados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06550-103">Miscellaneous Data Types (Visual Basic)</span></span>

<span data-ttu-id="06550-104">Visual Basic proporciona varios tipos de datos que no están orientados a números o caracteres.</span><span class="sxs-lookup"><span data-stu-id="06550-104">Visual Basic supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="06550-105">En su lugar, se ocupan de los datos especializados, como los valores sí/no, los valores de fecha y hora y las direcciones de objeto.</span><span class="sxs-lookup"><span data-stu-id="06550-105">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="06550-106">Para ver una tabla que muestra una comparación en paralelo de los tipos de datos Visual Basic, vea [tipos de datos](../../../language-reference/data-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="06550-106">For a table showing a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../language-reference/data-types/index.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="06550-107">Tipo booleano</span><span class="sxs-lookup"><span data-stu-id="06550-107">Boolean Type</span></span>  

 <span data-ttu-id="06550-108">El [tipo de datos Boolean](../../../language-reference/data-types/boolean-data-type.md) es un valor sin signo que se interpreta como `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="06550-108">The [Boolean Data Type](../../../language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="06550-109">El ancho de los datos depende de la plataforma de implementación.</span><span class="sxs-lookup"><span data-stu-id="06550-109">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="06550-110">Si una variable solo puede contener valores de dos Estados, como true/false, yes/no o ON/OFF, declárela como `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="06550-110">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="06550-111">Tipo de fecha</span><span class="sxs-lookup"><span data-stu-id="06550-111">Date Type</span></span>  

 <span data-ttu-id="06550-112">El [tipo de datos Date](../../../language-reference/data-types/date-data-type.md) es un valor de 64 bits que contiene información de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="06550-112">The [Date Data Type](../../../language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="06550-113">Cada incremento representa 100 nanosegundos de tiempo transcurrido desde el inicio (12:00 A.M.) del 1 de enero del año 1 del calendario gregoriano.</span><span class="sxs-lookup"><span data-stu-id="06550-113">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="06550-114">Si una variable puede contener un valor de fecha, un valor de hora o ambos, declárelo como `Date` .</span><span class="sxs-lookup"><span data-stu-id="06550-114">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="06550-115">Tipo de objeto</span><span class="sxs-lookup"><span data-stu-id="06550-115">Object Type</span></span>  

 <span data-ttu-id="06550-116">El [tipo de datos Object](../../../language-reference/data-types/object-data-type.md) es una dirección de 32 bits que apunta a una instancia de objeto dentro de la aplicación o en alguna otra aplicación.</span><span class="sxs-lookup"><span data-stu-id="06550-116">The [Object Data Type](../../../language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="06550-117">Una `Object` variable puede hacer referencia a cualquier objeto que la aplicación reconozca o a datos de cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="06550-117">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="06550-118">Esto incluye los dos *tipos de valor*, como `Integer` , `Boolean` y las instancias de la estructura, y los *tipos de referencia*, que son instancias de los objetos creados a partir de clases como `String` y <xref:System.Windows.Forms.Form> , y instancias de matriz.</span><span class="sxs-lookup"><span data-stu-id="06550-118">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="06550-119">Si una variable almacena un puntero a una instancia de una clase que no conoce en tiempo de compilación, o si puede apuntar a datos de varios tipos de datos, declárelo como `Object` .</span><span class="sxs-lookup"><span data-stu-id="06550-119">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="06550-120">La ventaja del `Object` tipo de datos es que se puede usar para almacenar datos de cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="06550-120">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="06550-121">El inconveniente es que se incurre en operaciones adicionales que tardan más tiempo de ejecución y hacen que la aplicación funcione más lentamente.</span><span class="sxs-lookup"><span data-stu-id="06550-121">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="06550-122">Si utiliza una `Object` variable para los tipos de valor, incurrirá en la *conversión boxing* y la conversión *unboxing*.</span><span class="sxs-lookup"><span data-stu-id="06550-122">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="06550-123">Si se usa para los tipos de referencia, se incurre en el *enlace en tiempo de ejecución*.</span><span class="sxs-lookup"><span data-stu-id="06550-123">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06550-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06550-124">See also</span></span>

- [<span data-ttu-id="06550-125">Caracteres de tipo</span><span class="sxs-lookup"><span data-stu-id="06550-125">Type Characters</span></span>](type-characters.md)
- [<span data-ttu-id="06550-126">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="06550-126">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="06550-127">Tipos de datos numéricos</span><span class="sxs-lookup"><span data-stu-id="06550-127">Numeric Data Types</span></span>](numeric-data-types.md)
- [<span data-ttu-id="06550-128">Tipos de datos de caracteres</span><span class="sxs-lookup"><span data-stu-id="06550-128">Character Data Types</span></span>](character-data-types.md)
- [<span data-ttu-id="06550-129">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="06550-129">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="06550-130">Enlace en tiempo de compilación y en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="06550-130">Early and Late Binding</span></span>](../early-late-binding/index.md)
