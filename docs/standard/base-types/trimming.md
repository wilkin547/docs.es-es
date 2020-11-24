---
title: Recorte y eliminación de caracteres de cadenas en .NET
description: Descubra cómo recortar los espacios en blanco del principio o del final de una cadena, o cómo quitar cualquier número de espacios o caracteres de una posición especificada de la cadena en .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET], removing characters
- Remove method
- TrimEnd method
- Trim method
- trimming characters
- TrimStart method
- removing characters
ms.assetid: ab248dab-70d4-4413-81c6-542d153fd195
ms.openlocfilehash: 8bc2980aa887dc652485e135058b9f6f718e7b45
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831278"
---
# <a name="trimming-and-removing-characters-from-strings-in-net"></a><span data-ttu-id="85f5a-103">Recorte y eliminación de caracteres de cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="85f5a-103">Trimming and Removing Characters from Strings in .NET</span></span>
<span data-ttu-id="85f5a-104">Si va a analizar una frase en las palabras que la forman, el resultado pueden ser palabras con espacios en blanco delante y detrás.</span><span class="sxs-lookup"><span data-stu-id="85f5a-104">If you are parsing a sentence into individual words, you might end up with words that have blank spaces (also called white spaces) on either end of the word.</span></span> <span data-ttu-id="85f5a-105">En este caso, puede usar uno de los métodos de recorte de la clase **System.String** para quitar espacios u otros caracteres de una posición especificada de la cadena.</span><span class="sxs-lookup"><span data-stu-id="85f5a-105">In this situation, you can use one of the trim methods in the **System.String** class to remove any number of spaces or other characters from a specified position in the string.</span></span> <span data-ttu-id="85f5a-106">En la tabla siguiente se describen los métodos de recorte disponibles.</span><span class="sxs-lookup"><span data-stu-id="85f5a-106">The following table describes the available trim methods.</span></span>  
  
|<span data-ttu-id="85f5a-107">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="85f5a-107">Method name</span></span>|<span data-ttu-id="85f5a-108">Usar</span><span class="sxs-lookup"><span data-stu-id="85f5a-108">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Trim%2A?displayProperty=nameWithType>|<span data-ttu-id="85f5a-109">Quita del comienzo y del final de una cadena los espacios en blanco o los caracteres especificados en una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="85f5a-109">Removes white spaces or characters specified in an array of characters from the beginning and end of a string.</span></span>|  
|<xref:System.String.TrimEnd%2A?displayProperty=nameWithType>|<span data-ttu-id="85f5a-110">Quita los caracteres especificados de una matriz de caracteres del final de una cadena.</span><span class="sxs-lookup"><span data-stu-id="85f5a-110">Removes characters specified in an array of characters from the end of a string.</span></span>|  
|<xref:System.String.TrimStart%2A?displayProperty=nameWithType>|<span data-ttu-id="85f5a-111">Quita los caracteres especificados de una matriz de caracteres del comienzo de una cadena.</span><span class="sxs-lookup"><span data-stu-id="85f5a-111">Removes characters specified in an array of characters from the beginning of a string.</span></span>|  
|<xref:System.String.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="85f5a-112">Quita un número especificado de caracteres de una posición de índice especificada de una cadena.</span><span class="sxs-lookup"><span data-stu-id="85f5a-112">Removes a specified number of characters from a specified index position in a string.</span></span>|  
  
## <a name="trim"></a><span data-ttu-id="85f5a-113">Trim</span><span class="sxs-lookup"><span data-stu-id="85f5a-113">Trim</span></span>

 <span data-ttu-id="85f5a-114">Los espacios en blanco situados delante y detrás de una cadena se pueden quitar fácilmente con el método <xref:System.String.Trim%2A?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="85f5a-114">You can easily remove white spaces from both ends of a string by using the <xref:System.String.Trim%2A?displayProperty=nameWithType> method, as shown in the following example.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#17)]
 [!code-csharp[Conceptual.String.BasicOps#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#17)]
 [!code-vb[Conceptual.String.BasicOps#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#17)]  
  
 <span data-ttu-id="85f5a-115">También se pueden quitar del principio y el final de una cadena los caracteres especificados en una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="85f5a-115">You can also remove characters that you specify in a character array from the beginning and end of a string.</span></span> <span data-ttu-id="85f5a-116">En el ejemplo siguiente se quitan los caracteres de espacio en blanco, los puntos y asteriscos.</span><span class="sxs-lookup"><span data-stu-id="85f5a-116">The following example removes white-space characters, periods, and asterisks.</span></span>  
  
 [!code-csharp[Conceptual.String.BasicOps#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trim2.cs#22)]
 [!code-vb[Conceptual.String.BasicOps#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trim2.vb#22)]  
  
## <a name="trimend"></a><span data-ttu-id="85f5a-117">TrimEnd</span><span class="sxs-lookup"><span data-stu-id="85f5a-117">TrimEnd</span></span>

 <span data-ttu-id="85f5a-118">El método **String.TrimEnd** quita caracteres del final de una cadena, creando un nuevo objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="85f5a-118">The **String.TrimEnd** method removes characters from the end of a string, creating a new string object.</span></span> <span data-ttu-id="85f5a-119">A este método se le pasa una matriz de caracteres para especificar los caracteres que se van a quitar.</span><span class="sxs-lookup"><span data-stu-id="85f5a-119">An array of characters is passed to this method to specify the characters to be removed.</span></span> <span data-ttu-id="85f5a-120">El orden de los elementos en la matriz de caracteres no afecta a la operación de recorte.</span><span class="sxs-lookup"><span data-stu-id="85f5a-120">The order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="85f5a-121">El recorte se detiene cuando se encuentra un carácter no especificado en la matriz.</span><span class="sxs-lookup"><span data-stu-id="85f5a-121">The trim stops when a character not specified in the array is found.</span></span>  
  
 <span data-ttu-id="85f5a-122">En el ejemplo siguiente se quitan las últimas letras de una cadena con el método **TrimEnd**.</span><span class="sxs-lookup"><span data-stu-id="85f5a-122">The following example removes the last letters of a string using the **TrimEnd** method.</span></span> <span data-ttu-id="85f5a-123">En este ejemplo, se invierte la posición de los caracteres `'r'` y `'W'` para ilustrar que el orden de los caracteres en la matriz no tiene importancia.</span><span class="sxs-lookup"><span data-stu-id="85f5a-123">In this example, the position of the `'r'` character and the `'W'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span> <span data-ttu-id="85f5a-124">Observe que este código quita la última palabra de `MyString` y parte de la primera.</span><span class="sxs-lookup"><span data-stu-id="85f5a-124">Notice that this code removes the last word of `MyString` plus part of the first.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#18)]
 [!code-csharp[Conceptual.String.BasicOps#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#18)]
 [!code-vb[Conceptual.String.BasicOps#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#18)]  
  
 <span data-ttu-id="85f5a-125">Con este código se muestra `He` en la consola.</span><span class="sxs-lookup"><span data-stu-id="85f5a-125">This code displays `He` to the console.</span></span>  
  
 <span data-ttu-id="85f5a-126">En el ejemplo siguiente se quita la última palabra de una cadena con el método **TrimEnd**.</span><span class="sxs-lookup"><span data-stu-id="85f5a-126">The following example removes the last word of a string using the **TrimEnd** method.</span></span> <span data-ttu-id="85f5a-127">En este código hay una coma después de `Hello` y, como la coma no está especificada en la matriz de caracteres que se deben recortar, la operación se detiene en la coma.</span><span class="sxs-lookup"><span data-stu-id="85f5a-127">In this code, a comma follows the word `Hello` and, because the comma is not specified in the array of characters to trim, the trim ends at the comma.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#19)]
 [!code-csharp[Conceptual.String.BasicOps#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#19)]
 [!code-vb[Conceptual.String.BasicOps#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#19)]  
  
 <span data-ttu-id="85f5a-128">Con este código se muestra `Hello,` en la consola.</span><span class="sxs-lookup"><span data-stu-id="85f5a-128">This code displays `Hello,` to the console.</span></span>  
  
## <a name="trimstart"></a><span data-ttu-id="85f5a-129">TrimStart</span><span class="sxs-lookup"><span data-stu-id="85f5a-129">TrimStart</span></span>

 <span data-ttu-id="85f5a-130">El método **String.TrimStart** es parecido al método **String.TrimEnd**, con la diferencia de que crea una nueva cadena quitando caracteres del comienzo de un objeto de cadena existente.</span><span class="sxs-lookup"><span data-stu-id="85f5a-130">The **String.TrimStart** method is similar to the **String.TrimEnd** method except that it creates a new string by removing characters from the beginning of an existing string object.</span></span> <span data-ttu-id="85f5a-131">Al método **TrimStart** se le pasa una matriz de caracteres para especificar los caracteres que se van a quitar.</span><span class="sxs-lookup"><span data-stu-id="85f5a-131">An array of characters is passed to the **TrimStart** method to specify the characters to be removed.</span></span> <span data-ttu-id="85f5a-132">Lo mismo que en el método **TrimEnd**, el orden de los elementos en la matriz de caracteres no afecta a la operación de recorte.</span><span class="sxs-lookup"><span data-stu-id="85f5a-132">As with the **TrimEnd** method, the order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="85f5a-133">El recorte se detiene cuando se encuentra un carácter no especificado en la matriz.</span><span class="sxs-lookup"><span data-stu-id="85f5a-133">The trim stops when a character not specified in the array is found.</span></span>  
  
 <span data-ttu-id="85f5a-134">En el siguiente ejemplo se quita la primera palabra de una cadena.</span><span class="sxs-lookup"><span data-stu-id="85f5a-134">The following example removes the first word of a string.</span></span> <span data-ttu-id="85f5a-135">En este ejemplo, se invierte la posición de los caracteres `'l'` y `'H'` para ilustrar que el orden de los caracteres en la matriz no tiene importancia.</span><span class="sxs-lookup"><span data-stu-id="85f5a-135">In this example, the position of the `'l'` character and the `'H'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#20)]
 [!code-csharp[Conceptual.String.BasicOps#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#20)]
 [!code-vb[Conceptual.String.BasicOps#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#20)]  
  
 <span data-ttu-id="85f5a-136">Con este código se muestra `World!` en la consola.</span><span class="sxs-lookup"><span data-stu-id="85f5a-136">This code displays `World!` to the console.</span></span>  
  
## <a name="remove"></a><span data-ttu-id="85f5a-137">Quitar</span><span class="sxs-lookup"><span data-stu-id="85f5a-137">Remove</span></span>

 <span data-ttu-id="85f5a-138">El método <xref:System.String.Remove%2A?displayProperty=nameWithType> quita un número especificado de caracteres, comenzando en una posición especificada de una cadena existente.</span><span class="sxs-lookup"><span data-stu-id="85f5a-138">The <xref:System.String.Remove%2A?displayProperty=nameWithType> method removes a specified number of characters that begin at a specified position in an existing string.</span></span> <span data-ttu-id="85f5a-139">Este método utiliza un índice basado en cero.</span><span class="sxs-lookup"><span data-stu-id="85f5a-139">This method assumes a zero-based index.</span></span>  
  
 <span data-ttu-id="85f5a-140">En el ejemplo siguiente se quitan diez caracteres de una cadena, comenzando en la posición cinco de un índice de base cero de la cadena.</span><span class="sxs-lookup"><span data-stu-id="85f5a-140">The following example removes ten characters from a string beginning at position five of a zero-based index of the string.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#21)]
 [!code-csharp[Conceptual.String.BasicOps#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#21)]
 [!code-vb[Conceptual.String.BasicOps#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#21)]  
  
## <a name="replace"></a><span data-ttu-id="85f5a-141">Sustituya</span><span class="sxs-lookup"><span data-stu-id="85f5a-141">Replace</span></span>

 <span data-ttu-id="85f5a-142">También puede quitar un carácter o una subcadena de una cadena llamando al método <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType> y especificando una cadena vacía (<xref:System.String.Empty?displayProperty=nameWithType>) como reemplazo.</span><span class="sxs-lookup"><span data-stu-id="85f5a-142">You can also remove a specified character or substring from a string by calling the <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType> method and specifying an empty string (<xref:System.String.Empty?displayProperty=nameWithType>) as the replacement.</span></span> <span data-ttu-id="85f5a-143">En el ejemplo siguiente se quitan todas las comas de una cadena.</span><span class="sxs-lookup"><span data-stu-id="85f5a-143">The following example removes all commas from a string.</span></span>  
  
 [!code-csharp[Conceptual.String.BasicOps#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/replace1.cs#23)]
 [!code-vb[Conceptual.String.BasicOps#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/replace1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="85f5a-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="85f5a-144">See also</span></span>

- [<span data-ttu-id="85f5a-145">Operaciones básicas de cadenas</span><span class="sxs-lookup"><span data-stu-id="85f5a-145">Basic String Operations</span></span>](basic-string-operations.md)
