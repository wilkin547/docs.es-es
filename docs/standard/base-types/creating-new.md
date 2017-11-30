---
title: Crear cadenas nuevas en .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CopyTo method
- Join method
- Format method
- Concat method
- strings [.NET Framework], creating
- Insert method
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d000cd88fc9ee9fd48ef25e9bb4982688564a2a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="creating-new-strings-in-net"></a><span data-ttu-id="6851c-102">Crear cadenas nuevas en .NET</span><span class="sxs-lookup"><span data-stu-id="6851c-102">Creating New Strings in .NET</span></span>
<span data-ttu-id="6851c-103">El [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] permite que las cadenas que se cree mediante asignación simple y también sobrecarga un constructor de clase para admitir la creación de cadenas mediante un número de parámetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="6851c-103">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="6851c-104">El [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] también proporciona varios métodos en la <xref:System.String?displayProperty=nameWithType> clase que crea la nueva cadena de objetos mediante la combinación de varias cadenas, matrices de cadenas u objetos.</span><span class="sxs-lookup"><span data-stu-id="6851c-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] also provides several methods in the <xref:System.String?displayProperty=nameWithType> class that create new string objects by combining several strings, arrays of strings, or objects.</span></span>  
  
## <a name="creating-strings-using-assignment"></a><span data-ttu-id="6851c-105">Creación de cadenas mediante asignaciones</span><span class="sxs-lookup"><span data-stu-id="6851c-105">Creating Strings Using Assignment</span></span>  
 <span data-ttu-id="6851c-106">La manera más fácil de crear un nuevo <xref:System.String> objeto simplemente consiste en asignar un literal de cadena a un <xref:System.String> objeto.</span><span class="sxs-lookup"><span data-stu-id="6851c-106">The easiest way to create a new <xref:System.String> object is simply to assign a string literal to a <xref:System.String> object.</span></span>  
  
## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="6851c-107">Creación de cadenas mediante un constructor de clase</span><span class="sxs-lookup"><span data-stu-id="6851c-107">Creating Strings Using a Class Constructor</span></span>  
 <span data-ttu-id="6851c-108">Puede utilizar las sobrecargas de los <xref:System.String> constructor de clase para crear cadenas de matrices de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6851c-108">You can use overloads of the <xref:System.String> class constructor to create strings from character arrays.</span></span> <span data-ttu-id="6851c-109">También puede crear una nueva cadena al duplicar un determinado carácter un número especificado de veces.</span><span class="sxs-lookup"><span data-stu-id="6851c-109">You can also create a new string by duplicating a particular character a specified number of times.</span></span>  
  
## <a name="methods-that-return-strings"></a><span data-ttu-id="6851c-110">Métodos que devuelven cadenas</span><span class="sxs-lookup"><span data-stu-id="6851c-110">Methods that Return Strings</span></span>  
 <span data-ttu-id="6851c-111">En la tabla siguiente se enumeran varios métodos útiles que devuelven nuevos objetos de cadena.</span><span class="sxs-lookup"><span data-stu-id="6851c-111">The following table lists several useful methods that return new string objects.</span></span>  
  
|<span data-ttu-id="6851c-112">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="6851c-112">Method name</span></span>|<span data-ttu-id="6851c-113">Uso</span><span class="sxs-lookup"><span data-stu-id="6851c-113">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|<span data-ttu-id="6851c-114">Compila una cadena con formato a partir de un conjunto de objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="6851c-114">Builds a formatted string from a set of input objects.</span></span>|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|<span data-ttu-id="6851c-115">Compila cadenas a partir de dos o más cadenas.</span><span class="sxs-lookup"><span data-stu-id="6851c-115">Builds strings from two or more strings.</span></span>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|<span data-ttu-id="6851c-116">Compila una nueva cadena al combinar una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="6851c-116">Builds a new string by combining an array of strings.</span></span>|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|<span data-ttu-id="6851c-117">Compila una nueva cadena al insertar una cadena en el índice especificado de una cadena existente.</span><span class="sxs-lookup"><span data-stu-id="6851c-117">Builds a new string by inserting a string into the specified index of an existing string.</span></span>|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|<span data-ttu-id="6851c-118">Copia los caracteres especificados de una cadena en la posición especificada de una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6851c-118">Copies specified characters in a string into a specified position in an array of characters.</span></span>|  
  
### <a name="format"></a><span data-ttu-id="6851c-119">Formato</span><span class="sxs-lookup"><span data-stu-id="6851c-119">Format</span></span>  
 <span data-ttu-id="6851c-120">Puede usar el **String.Format** método para crear cadenas con formato y concatenar cadenas que representan varios objetos.</span><span class="sxs-lookup"><span data-stu-id="6851c-120">You can use the **String.Format** method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="6851c-121">Este método convierte automáticamente cualquier objeto pasado en una cadena.</span><span class="sxs-lookup"><span data-stu-id="6851c-121">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="6851c-122">Por ejemplo, si la aplicación debe mostrar un **Int32** valor y un **DateTime** valor para el usuario, puede crear fácilmente una cadena que represente estos valores con el **formato**(método).</span><span class="sxs-lookup"><span data-stu-id="6851c-122">For example, if your application must display an **Int32** value and a **DateTime** value to the user, you can easily construct a string to represent these values using the **Format** method.</span></span> <span data-ttu-id="6851c-123">Para más información sobre las convenciones de formato usadas con este método, consulte la sección sobre [formatos compuestos](../../../docs/standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="6851c-123">For information about formatting conventions used with this method, see the section on [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>  
  
 <span data-ttu-id="6851c-124">En el ejemplo siguiente se usa el **formato** método para crear una cadena que usa una variable de entero.</span><span class="sxs-lookup"><span data-stu-id="6851c-124">The following example uses the **Format** method to create a string that uses an integer variable.</span></span>  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 <span data-ttu-id="6851c-125">En este ejemplo,<xref:System.DateTime.Now%2A?displayProperty=nameWithType> muestra la fecha y hora actuales en el formato especificado por la referencia cultural asociada al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="6851c-125">In this example,<xref:System.DateTime.Now%2A?displayProperty=nameWithType> displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>  
  
### <a name="concat"></a><span data-ttu-id="6851c-126">Concat</span><span class="sxs-lookup"><span data-stu-id="6851c-126">Concat</span></span>  
 <span data-ttu-id="6851c-127">El **String.Concat** método se puede utilizar para crear fácilmente un nuevo objeto de cadena de dos o más objetos existentes.</span><span class="sxs-lookup"><span data-stu-id="6851c-127">The **String.Concat** method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="6851c-128">Proporciona una manera independiente del lenguaje de concatenar cadenas.</span><span class="sxs-lookup"><span data-stu-id="6851c-128">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="6851c-129">Este método acepta cualquier clase que deriva de **System.Object**.</span><span class="sxs-lookup"><span data-stu-id="6851c-129">This method accepts any class that derives from **System.Object**.</span></span> <span data-ttu-id="6851c-130">En el ejemplo siguiente se crea una cadena a partir de dos objetos de cadena existentes y un carácter de separación.</span><span class="sxs-lookup"><span data-stu-id="6851c-130">The following example creates a string from two existing string objects and a separating character.</span></span>  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a><span data-ttu-id="6851c-131">Join</span><span class="sxs-lookup"><span data-stu-id="6851c-131">Join</span></span>  
 <span data-ttu-id="6851c-132">El **String.Join** método crea una nueva cadena de una matriz de cadenas y una cadena de separación.</span><span class="sxs-lookup"><span data-stu-id="6851c-132">The **String.Join** method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="6851c-133">Este método resulta útil si quiere concatenar varias cadenas para formar una lista quizás separada por una coma.</span><span class="sxs-lookup"><span data-stu-id="6851c-133">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>  
  
 <span data-ttu-id="6851c-134">En el ejemplo siguiente se usa un espacio para enlazar una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="6851c-134">The following example uses a space to bind a string array.</span></span>  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a><span data-ttu-id="6851c-135">Insertar</span><span class="sxs-lookup"><span data-stu-id="6851c-135">Insert</span></span>  
 <span data-ttu-id="6851c-136">El **String.Insert** método crea una nueva cadena insertando una cadena en una posición especificada en otra cadena.</span><span class="sxs-lookup"><span data-stu-id="6851c-136">The **String.Insert** method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="6851c-137">Este método usa un índice basado en cero.</span><span class="sxs-lookup"><span data-stu-id="6851c-137">This method uses a zero-based index.</span></span> <span data-ttu-id="6851c-138">En el ejemplo siguiente se inserta una cadena en la quinta posición del índice de `MyString` y se crea una nueva cadena con este valor.</span><span class="sxs-lookup"><span data-stu-id="6851c-138">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a><span data-ttu-id="6851c-139">CopyTo</span><span class="sxs-lookup"><span data-stu-id="6851c-139">CopyTo</span></span>  
 <span data-ttu-id="6851c-140">El **String.CopyTo** método copia las partes de una cadena en una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6851c-140">The **String.CopyTo** method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="6851c-141">Puede especificar el índice inicial de la cadena y el número de caracteres que se va a copiar.</span><span class="sxs-lookup"><span data-stu-id="6851c-141">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="6851c-142">Este método toma el índice de origen, una matriz de caracteres, el índice de destino y el número de caracteres que se va a copiar.</span><span class="sxs-lookup"><span data-stu-id="6851c-142">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="6851c-143">Todos los índices se basan en cero.</span><span class="sxs-lookup"><span data-stu-id="6851c-143">All indexes are zero-based.</span></span>  
  
 <span data-ttu-id="6851c-144">En el ejemplo siguiente se usa el **CopyTo** method para copiar los caracteres de la palabra "Hola" de una cadena de objetos a la primera posición de índice de una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6851c-144">The following example uses the **CopyTo** method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="6851c-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="6851c-145">See Also</span></span>  
 [<span data-ttu-id="6851c-146">Operaciones básicas de cadenas</span><span class="sxs-lookup"><span data-stu-id="6851c-146">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)  
 [<span data-ttu-id="6851c-147">Formatos compuestos</span><span class="sxs-lookup"><span data-stu-id="6851c-147">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)
