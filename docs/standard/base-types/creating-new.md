---
title: Creación de cadenas en .NET
description: Aprenda a crear cadenas mediante asignación, constructores de clase o métodos System.String que combinan varias cadenas, matrices de cadenas u objetos en .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CopyTo method
- Join method
- Format method
- Concat method
- strings [.NET], creating
- Insert method
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
ms.openlocfilehash: 7dedaf61f56f19343299c841bb4cee70fb9c767a
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889444"
---
# <a name="creating-new-strings-in-net"></a><span data-ttu-id="9150f-103">Creación de cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="9150f-103">Creating New Strings in .NET</span></span>

<span data-ttu-id="9150f-104">.NET permite crear cadenas mediante asignaciones simples y, además, sobrecarga un constructor de clases para admitir la creación de cadenas mediante una serie de parámetros.</span><span class="sxs-lookup"><span data-stu-id="9150f-104">.NET allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="9150f-105">.NET también proporciona varios métodos en la clase <xref:System.String?displayProperty=nameWithType> que crean objetos de cadena mediante la combinación de varias cadenas, matrices de cadenas u objetos.</span><span class="sxs-lookup"><span data-stu-id="9150f-105">.NET also provides several methods in the <xref:System.String?displayProperty=nameWithType> class that create new string objects by combining several strings, arrays of strings, or objects.</span></span>  
  
## <a name="creating-strings-using-assignment"></a><span data-ttu-id="9150f-106">Creación de cadenas mediante asignaciones</span><span class="sxs-lookup"><span data-stu-id="9150f-106">Creating Strings Using Assignment</span></span>  
 <span data-ttu-id="9150f-107">La manera más sencilla de crear un objeto <xref:System.String> es asignar un literal de cadena a un objeto <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="9150f-107">The easiest way to create a new <xref:System.String> object is simply to assign a string literal to a <xref:System.String> object.</span></span>  
  
## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="9150f-108">Creación de cadenas mediante un constructor de clase</span><span class="sxs-lookup"><span data-stu-id="9150f-108">Creating Strings Using a Class Constructor</span></span>  
 <span data-ttu-id="9150f-109">Puede usar las sobrecargas del constructor de clases <xref:System.String> para crear cadenas a partir de matrices de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9150f-109">You can use overloads of the <xref:System.String> class constructor to create strings from character arrays.</span></span> <span data-ttu-id="9150f-110">También puede crear una nueva cadena al duplicar un determinado carácter un número especificado de veces.</span><span class="sxs-lookup"><span data-stu-id="9150f-110">You can also create a new string by duplicating a particular character a specified number of times.</span></span>  
  
## <a name="methods-that-return-strings"></a><span data-ttu-id="9150f-111">Métodos que devuelven cadenas</span><span class="sxs-lookup"><span data-stu-id="9150f-111">Methods that Return Strings</span></span>  
 <span data-ttu-id="9150f-112">En la tabla siguiente se enumeran varios métodos útiles que devuelven nuevos objetos de cadena.</span><span class="sxs-lookup"><span data-stu-id="9150f-112">The following table lists several useful methods that return new string objects.</span></span>  
  
|<span data-ttu-id="9150f-113">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="9150f-113">Method name</span></span>|<span data-ttu-id="9150f-114">Usar</span><span class="sxs-lookup"><span data-stu-id="9150f-114">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|<span data-ttu-id="9150f-115">Compila una cadena con formato a partir de un conjunto de objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="9150f-115">Builds a formatted string from a set of input objects.</span></span>|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|<span data-ttu-id="9150f-116">Compila cadenas a partir de dos o más cadenas.</span><span class="sxs-lookup"><span data-stu-id="9150f-116">Builds strings from two or more strings.</span></span>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|<span data-ttu-id="9150f-117">Compila una nueva cadena al combinar una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="9150f-117">Builds a new string by combining an array of strings.</span></span>|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|<span data-ttu-id="9150f-118">Compila una nueva cadena al insertar una cadena en el índice especificado de una cadena existente.</span><span class="sxs-lookup"><span data-stu-id="9150f-118">Builds a new string by inserting a string into the specified index of an existing string.</span></span>|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|<span data-ttu-id="9150f-119">Copia los caracteres especificados de una cadena en la posición especificada de una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9150f-119">Copies specified characters in a string into a specified position in an array of characters.</span></span>|  
  
### <a name="format"></a><span data-ttu-id="9150f-120">Formato</span><span class="sxs-lookup"><span data-stu-id="9150f-120">Format</span></span>  
 <span data-ttu-id="9150f-121">Puede usar el método **String.Format** para crear cadenas con formato y concatenar cadenas que representan a varios objetos.</span><span class="sxs-lookup"><span data-stu-id="9150f-121">You can use the **String.Format** method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="9150f-122">Este método convierte automáticamente cualquier objeto pasado en una cadena.</span><span class="sxs-lookup"><span data-stu-id="9150f-122">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="9150f-123">Por ejemplo, si la aplicación debe mostrar un valor **Int32** y un valor **DateTime** al usuario, puede construir fácilmente una cadena para representar estos valores con el método **Format**.</span><span class="sxs-lookup"><span data-stu-id="9150f-123">For example, if your application must display an **Int32** value and a **DateTime** value to the user, you can easily construct a string to represent these values using the **Format** method.</span></span> <span data-ttu-id="9150f-124">Para más información sobre las convenciones de formato usadas con este método, consulte la sección sobre [formatos compuestos](composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="9150f-124">For information about formatting conventions used with this method, see the section on [composite formatting](composite-formatting.md).</span></span>  
  
 <span data-ttu-id="9150f-125">En el ejemplo siguiente se usa el método **Format** para crear una cadena que emplea una variable de entero.</span><span class="sxs-lookup"><span data-stu-id="9150f-125">The following example uses the **Format** method to create a string that uses an integer variable.</span></span>  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 <span data-ttu-id="9150f-126">En este ejemplo, <xref:System.DateTime.Now%2A?displayProperty=nameWithType> muestra la fecha y hora actuales en el formato especificado por la referencia cultural asociada al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="9150f-126">In this example,<xref:System.DateTime.Now%2A?displayProperty=nameWithType> displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>  
  
### <a name="concat"></a><span data-ttu-id="9150f-127">Concat</span><span class="sxs-lookup"><span data-stu-id="9150f-127">Concat</span></span>  
 <span data-ttu-id="9150f-128">El método **String.Concat** se puede usar para crear fácilmente un objeto de cadena a partir de dos o más objetos existentes.</span><span class="sxs-lookup"><span data-stu-id="9150f-128">The **String.Concat** method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="9150f-129">Proporciona una manera independiente del lenguaje de concatenar cadenas.</span><span class="sxs-lookup"><span data-stu-id="9150f-129">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="9150f-130">Este método acepta cualquier clase que derive de **System.Object**.</span><span class="sxs-lookup"><span data-stu-id="9150f-130">This method accepts any class that derives from **System.Object**.</span></span> <span data-ttu-id="9150f-131">En el ejemplo siguiente se crea una cadena a partir de dos objetos de cadena existentes y un carácter de separación.</span><span class="sxs-lookup"><span data-stu-id="9150f-131">The following example creates a string from two existing string objects and a separating character.</span></span>  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a><span data-ttu-id="9150f-132">Join</span><span class="sxs-lookup"><span data-stu-id="9150f-132">Join</span></span>  
 <span data-ttu-id="9150f-133">El método **String.Join** crea una cadena a partir de una matriz de cadenas y una cadena separadora.</span><span class="sxs-lookup"><span data-stu-id="9150f-133">The **String.Join** method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="9150f-134">Este método resulta útil si quiere concatenar varias cadenas para formar una lista quizás separada por una coma.</span><span class="sxs-lookup"><span data-stu-id="9150f-134">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>  
  
 <span data-ttu-id="9150f-135">En el ejemplo siguiente se usa un espacio para enlazar una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="9150f-135">The following example uses a space to bind a string array.</span></span>  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a><span data-ttu-id="9150f-136">Insertar</span><span class="sxs-lookup"><span data-stu-id="9150f-136">Insert</span></span>  
 <span data-ttu-id="9150f-137">El método **String.Insert** crea una cadena al insertar una cadena en la posición especificada de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="9150f-137">The **String.Insert** method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="9150f-138">Este método usa un índice basado en cero.</span><span class="sxs-lookup"><span data-stu-id="9150f-138">This method uses a zero-based index.</span></span> <span data-ttu-id="9150f-139">En el ejemplo siguiente se inserta una cadena en la quinta posición del índice de `MyString` y se crea una nueva cadena con este valor.</span><span class="sxs-lookup"><span data-stu-id="9150f-139">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a><span data-ttu-id="9150f-140">CopyTo</span><span class="sxs-lookup"><span data-stu-id="9150f-140">CopyTo</span></span>  
 <span data-ttu-id="9150f-141">El método **String.CopyTo** copia partes de una cadena en una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9150f-141">The **String.CopyTo** method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="9150f-142">Puede especificar el índice inicial de la cadena y el número de caracteres que se va a copiar.</span><span class="sxs-lookup"><span data-stu-id="9150f-142">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="9150f-143">Este método toma el índice de origen, una matriz de caracteres, el índice de destino y el número de caracteres que se va a copiar.</span><span class="sxs-lookup"><span data-stu-id="9150f-143">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="9150f-144">Todos los índices se basan en cero.</span><span class="sxs-lookup"><span data-stu-id="9150f-144">All indexes are zero-based.</span></span>  
  
 <span data-ttu-id="9150f-145">En el ejemplo siguiente se usa el método **CopyTo** para copiar los caracteres de la palabra "Hello" de un objeto de cadena en la primera posición del índice de una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9150f-145">The following example uses the **CopyTo** method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="9150f-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="9150f-146">See also</span></span>

- [<span data-ttu-id="9150f-147">Operaciones básicas de cadenas</span><span class="sxs-lookup"><span data-stu-id="9150f-147">Basic String Operations</span></span>](basic-string-operations.md)
- [<span data-ttu-id="9150f-148">Formatos compuestos</span><span class="sxs-lookup"><span data-stu-id="9150f-148">Composite Formatting</span></span>](composite-formatting.md)
