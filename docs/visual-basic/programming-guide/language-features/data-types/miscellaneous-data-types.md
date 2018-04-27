---
title: Tipos de datos variados (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f80aacccab4c215b3e3917cc73097080aa6b9941
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="5fbe8-102">Tipos de datos variados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5fbe8-102">Miscellaneous Data Types (Visual Basic)</span></span>
<span data-ttu-id="5fbe8-103">Visual Basic proporciona varios tipos de datos que no están orientados a caracteres o números.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-103">Visual Basic supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="5fbe8-104">En su lugar, tratan con datos especializado, como sí/no valores, valores de fecha/hora y direcciones de objetos.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="5fbe8-105">Para una tabla que muestra una comparación en paralelo de los tipos de datos de Visual Basic, vea [tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="5fbe8-105">For a table showing a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="5fbe8-106">Tipo booleano</span><span class="sxs-lookup"><span data-stu-id="5fbe8-106">Boolean Type</span></span>  
 <span data-ttu-id="5fbe8-107">El [tipo de datos Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) es un valor sin signo que se interpreta como `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="5fbe8-108">Su ancho de datos depende de la plataforma de implementación.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="5fbe8-109">Si una variable puede contener sólo valores de dos estados como verdadero/falso, sí/no, o activado/desactivado, declárela como `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="5fbe8-110">Date (tipo)</span><span class="sxs-lookup"><span data-stu-id="5fbe8-110">Date Type</span></span>  
 <span data-ttu-id="5fbe8-111">El [tipo de datos Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) es un valor de 64 bits que contiene información de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="5fbe8-112">Cada incremento representa 100 nanosegundos de tiempo transcurrido desde el principio (12:00 A.M.) del 1 de enero del año 1 del calendario gregoriano.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="5fbe8-113">Si una variable puede contener un valor de fecha, un valor de hora o ambas, declárelo como `Date`.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="5fbe8-114">Tipo de objeto</span><span class="sxs-lookup"><span data-stu-id="5fbe8-114">Object Type</span></span>  
 <span data-ttu-id="5fbe8-115">El [tipo de datos de objeto](../../../../visual-basic/language-reference/data-types/object-data-type.md) es una dirección de 32 bits que señala a una instancia de objeto dentro de la aplicación o en otra aplicación.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="5fbe8-116">Un `Object` variable puede hacer referencia a cualquier objeto de la aplicación reconoce o a datos de cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="5fbe8-117">Esto incluye tanto *los tipos de valor*, como `Integer`, `Boolean`y las instancias de la estructura, y *hacen referencia a tipos*, que son instancias de objetos creados a partir de clases como `String`y <xref:System.Windows.Forms.Form>y la matriz de instancias.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="5fbe8-118">Si una variable almacena un puntero a una instancia de una clase que no se conocen en tiempo de compilación, o si puede señalar a los datos de diversos tipos de datos, se declara como `Object`.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="5fbe8-119">La ventaja de la `Object` es de tipo de datos que puede usar para almacenar datos de cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="5fbe8-120">La desventaja es que se incurre en operaciones adicionales que tardan más tiempo de ejecución y que la aplicación se ejecute más lentamente.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="5fbe8-121">Si utiliza un `Object` variables para tipos de valor, se incurre en *conversión boxing* y *unboxing*.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="5fbe8-122">Si utiliza tipos de referencia, se incurre en *enlace más tarde*.</span><span class="sxs-lookup"><span data-stu-id="5fbe8-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fbe8-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fbe8-123">See Also</span></span>  
 [<span data-ttu-id="5fbe8-124">Caracteres de tipo</span><span class="sxs-lookup"><span data-stu-id="5fbe8-124">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="5fbe8-125">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="5fbe8-125">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="5fbe8-126">Tipos de datos numéricos</span><span class="sxs-lookup"><span data-stu-id="5fbe8-126">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [<span data-ttu-id="5fbe8-127">Tipos de datos de caracteres</span><span class="sxs-lookup"><span data-stu-id="5fbe8-127">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [<span data-ttu-id="5fbe8-128">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="5fbe8-128">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="5fbe8-129">Enlace en tiempo de compilación y en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5fbe8-129">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
