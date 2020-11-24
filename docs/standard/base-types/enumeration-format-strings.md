---
title: Cadenas de formato de enumeración
description: Cree cadenas de formato de enumeración con el método Enum.ToString en .NET. Asigne formato a los valores numéricos, hexadecimales o de cadena de los miembros de enumeración.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
ms.openlocfilehash: 02a12c36e47a82c15c01e578333e1c4465bab142
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829627"
---
# <a name="enumeration-format-strings"></a><span data-ttu-id="05e4a-104">Cadenas de formato de enumeración</span><span class="sxs-lookup"><span data-stu-id="05e4a-104">Enumeration format strings</span></span>

<span data-ttu-id="05e4a-105">Puede usar el método <xref:System.Enum.ToString%2A?displayProperty=nameWithType> para crear un objeto de cadena que represente el valor de cadena, numérico o hexadecimal del miembro de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="05e4a-105">You can use the <xref:System.Enum.ToString%2A?displayProperty=nameWithType> method to create a new string object that represents the numeric, hexadecimal, or string value of an enumeration member.</span></span> <span data-ttu-id="05e4a-106">Este método toma una de las cadenas de formato de enumeración para especificar el valor que quiere que se devuelva.</span><span class="sxs-lookup"><span data-stu-id="05e4a-106">This method takes one of the enumeration formatting strings to specify the value that you want returned.</span></span>

<span data-ttu-id="05e4a-107">En las secciones siguientes se enumeran las cadenas de formato de enumeración y los valores que devuelven.</span><span class="sxs-lookup"><span data-stu-id="05e4a-107">The following sections list the enumeration formatting strings and the values they return.</span></span> <span data-ttu-id="05e4a-108">Estos especificadores de formato no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="05e4a-108">These format specifiers are not case-sensitive.</span></span>

## <a name="g-or-g"></a><span data-ttu-id="05e4a-109">G o g</span><span class="sxs-lookup"><span data-stu-id="05e4a-109">G or g</span></span>

<span data-ttu-id="05e4a-110">Si es posible, muestra la entrada de enumeración como valor de cadena y, si no, muestra el valor entero de la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="05e4a-110">Displays the enumeration entry as a string value, if possible, and otherwise displays the integer value of the current instance.</span></span> <span data-ttu-id="05e4a-111">Si la enumeración se define con el conjunto de atributos **Flags**, los valores de cadena de cada entrada válida se concatenan, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="05e4a-111">If the enumeration is defined with the **Flags** attribute set, the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="05e4a-112">Si no se establece el atributo **Flags**, se muestra un valor no válido como entrada numérica.</span><span class="sxs-lookup"><span data-stu-id="05e4a-112">If the **Flags** attribute is not set, an invalid value is displayed as a numeric entry.</span></span> <span data-ttu-id="05e4a-113">En el siguiente ejemplo se muestra el uso del especificador de formato G.</span><span class="sxs-lookup"><span data-stu-id="05e4a-113">The following example illustrates the G format specifier.</span></span>

[!code-csharp[Formatting.Enum#1](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)]
[!code-vb[Formatting.Enum#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]

## <a name="f-or-f"></a><span data-ttu-id="05e4a-114">F o f</span><span class="sxs-lookup"><span data-stu-id="05e4a-114">F or f</span></span>

<span data-ttu-id="05e4a-115">Si es posible, muestra la entrada de enumeración como valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="05e4a-115">Displays the enumeration entry as a string value, if possible.</span></span> <span data-ttu-id="05e4a-116">Si el valor se puede mostrar por completo como suma de las entradas de la enumeración (aunque el atributo **Flags** no esté presente), los valores de cadena de cada entrada válida se concatenan, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="05e4a-116">If the value can be completely displayed as a summation of the entries in the enumeration (even if the **Flags** attribute is not present), the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="05e4a-117">Si las entradas de enumeración no pueden determinar completamente el valor, a este se le da formato como valor entero.</span><span class="sxs-lookup"><span data-stu-id="05e4a-117">If the value cannot be completely determined by the enumeration entries, then the value is formatted as the integer value.</span></span> <span data-ttu-id="05e4a-118">En el siguiente ejemplo se muestra el uso del especificador de formato F.</span><span class="sxs-lookup"><span data-stu-id="05e4a-118">The following example illustrates the F format specifier.</span></span>

[!code-csharp[Formatting.Enum#2](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)]
[!code-vb[Formatting.Enum#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]

## <a name="d-or-d"></a><span data-ttu-id="05e4a-119">D o d</span><span class="sxs-lookup"><span data-stu-id="05e4a-119">D or d</span></span>

<span data-ttu-id="05e4a-120">Muestra la entrada de enumeración como valor entero en la representación más corta posible.</span><span class="sxs-lookup"><span data-stu-id="05e4a-120">Displays the enumeration entry as an integer value in the shortest representation possible.</span></span> <span data-ttu-id="05e4a-121">En el siguiente ejemplo se muestra el uso del especificador de formato D.</span><span class="sxs-lookup"><span data-stu-id="05e4a-121">The following example illustrates the D format specifier.</span></span>

[!code-csharp[Formatting.Enum#3](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)]
[!code-vb[Formatting.Enum#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]

## <a name="x-or-x"></a><span data-ttu-id="05e4a-122">X o x</span><span class="sxs-lookup"><span data-stu-id="05e4a-122">X or x</span></span>

<span data-ttu-id="05e4a-123">Muestra la entrada de enumeración como valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="05e4a-123">Displays the enumeration entry as a hexadecimal value.</span></span> <span data-ttu-id="05e4a-124">El valor se representa con ceros a la izquierda, según sea necesario, para garantizar que la cadena de resultados tenga dos caracteres para cada byte en el [tipo numérico que subyace](xref:System.Enum.GetUnderlyingType%2A) en el tipo de enumeración.</span><span class="sxs-lookup"><span data-stu-id="05e4a-124">The value is represented with leading zeros as necessary, to ensure that the result string has two characters for each byte in the enumeration type's [underlying numeric type](xref:System.Enum.GetUnderlyingType%2A).</span></span> <span data-ttu-id="05e4a-125">En el siguiente ejemplo se muestra el uso del especificador de formato X.</span><span class="sxs-lookup"><span data-stu-id="05e4a-125">The following example illustrates the X format specifier.</span></span> <span data-ttu-id="05e4a-126">En el ejemplo, el tipo subyacente tanto de <xref:System.ConsoleColor> como de <xref:System.IO.FileAttributes> es <xref:System.Int32>, o un entero de 32 bits (o 4 bytes), que produce una cadena de resultados de ocho caracteres.</span><span class="sxs-lookup"><span data-stu-id="05e4a-126">In the example, the underlying type of both <xref:System.ConsoleColor> and <xref:System.IO.FileAttributes> is <xref:System.Int32>, or a 32-bit (or 4-byte) integer, which produces an 8-character result string.</span></span>

[!code-csharp[Formatting.Enum#4](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)]
[!code-vb[Formatting.Enum#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]

## <a name="example"></a><span data-ttu-id="05e4a-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="05e4a-127">Example</span></span>

<span data-ttu-id="05e4a-128">En el ejemplo siguiente se define una enumeración denominada `Colors` que consta de tres entradas: `Red`, `Blue` y `Green`.</span><span class="sxs-lookup"><span data-stu-id="05e4a-128">The following example defines an enumeration called `Colors` that consists of three entries: `Red`, `Blue`, and `Green`.</span></span>

[!code-csharp[Formatting.Enum#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
[!code-vb[Formatting.Enum#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]

<span data-ttu-id="05e4a-129">Una vez definida la enumeración, se puede declarar una instancia de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="05e4a-129">After the enumeration is defined, an instance can be declared in the following manner.</span></span>

[!code-csharp[Formatting.Enum#6](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
[!code-vb[Formatting.Enum#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]

<span data-ttu-id="05e4a-130">Luego se puede usar el método `Color.ToString(System.String)` para mostrar el valor de enumeración de maneras diferentes, según el especificador de formato pasado.</span><span class="sxs-lookup"><span data-stu-id="05e4a-130">The `Color.ToString(System.String)` method can then be used to display the enumeration value in different ways, depending on the format specifier passed to it.</span></span>

[!code-csharp[Formatting.Enum#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
[!code-vb[Formatting.Enum#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]

## <a name="see-also"></a><span data-ttu-id="05e4a-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="05e4a-131">See also</span></span>

- [<span data-ttu-id="05e4a-132">Aplicación de formato a tipos</span><span class="sxs-lookup"><span data-stu-id="05e4a-132">Formatting Types</span></span>](formatting-types.md)
