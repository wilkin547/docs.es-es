---
title: "Cadenas de formato de enumeración"
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
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET Framework], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 58004fa19f2ec3b1ca7570d6ca75702510148002
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="enumeration-format-strings"></a><span data-ttu-id="7a23d-102">Cadenas de formato de enumeración</span><span class="sxs-lookup"><span data-stu-id="7a23d-102">Enumeration Format Strings</span></span>
<span data-ttu-id="7a23d-103">Puede usar el método <xref:System.Enum.ToString%2A?displayProperty=nameWithType> para crear un objeto de cadena que represente el valor de cadena, numérico o hexadecimal del miembro de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="7a23d-103">You can use the <xref:System.Enum.ToString%2A?displayProperty=nameWithType> method to create a new string object that represents the numeric, hexadecimal, or string value of an enumeration member.</span></span> <span data-ttu-id="7a23d-104">Este método toma una de las cadenas de formato de enumeración para especificar el valor que quiere que se devuelva.</span><span class="sxs-lookup"><span data-stu-id="7a23d-104">This method takes one of the enumeration formatting strings to specify the value that you want returned.</span></span>  
  
 <span data-ttu-id="7a23d-105">En la tabla siguiente se enumeran las cadenas de formato de enumeración y los valores que devuelven.</span><span class="sxs-lookup"><span data-stu-id="7a23d-105">The following table lists the enumeration formatting strings and the values they return.</span></span> <span data-ttu-id="7a23d-106">Estos especificadores de formato no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7a23d-106">These format specifiers are not case-sensitive.</span></span>  
  
| <span data-ttu-id="7a23d-107">Cadena de formato</span><span class="sxs-lookup"><span data-stu-id="7a23d-107">Format string</span></span> | <span data-ttu-id="7a23d-108">Resultado</span><span class="sxs-lookup"><span data-stu-id="7a23d-108">Result</span></span> |  
| ------------- | ------ |  
| <span data-ttu-id="7a23d-109">G o g</span><span class="sxs-lookup"><span data-stu-id="7a23d-109">G or g</span></span> | <span data-ttu-id="7a23d-110">Si es posible, muestra la entrada de enumeración como valor de cadena y, si no, muestra el valor entero de la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="7a23d-110">Displays the enumeration entry as a string value, if possible, and otherwise displays the integer value of the current instance.</span></span> <span data-ttu-id="7a23d-111">Si la enumeración se define con el conjunto de atributos **Flags**, los valores de cadena de cada entrada válida se concatenan, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="7a23d-111">If the enumeration is defined with the **Flags** attribute set, the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="7a23d-112">Si no se establece el atributo **Flags**, se muestra un valor no válido como entrada numérica.</span><span class="sxs-lookup"><span data-stu-id="7a23d-112">If the **Flags** attribute is not set, an invalid value is displayed as a numeric entry.</span></span> <span data-ttu-id="7a23d-113">En el siguiente ejemplo se muestra el uso del especificador de formato G.</span><span class="sxs-lookup"><span data-stu-id="7a23d-113">The following example illustrates the G format specifier.</span></span><br><br><span data-ttu-id="7a23d-114">[!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)] [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="7a23d-114">[!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)] [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]</span></span> |  
| <span data-ttu-id="7a23d-115">F o f</span><span class="sxs-lookup"><span data-stu-id="7a23d-115">F or f</span></span> | <span data-ttu-id="7a23d-116">Si es posible, muestra la entrada de enumeración como valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="7a23d-116">Displays the enumeration entry as a string value, if possible.</span></span> <span data-ttu-id="7a23d-117">Si el valor se puede mostrar por completo como suma de las entradas de la enumeración (aunque el atributo **Flags** no esté presente), los valores de cadena de cada entrada válida se concatenan, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="7a23d-117">If the value can be completely displayed as a summation of the entries in the enumeration (even if the **Flags** attribute is not present), the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="7a23d-118">Si las entradas de enumeración no pueden determinar completamente el valor, a este se le da formato como valor entero.</span><span class="sxs-lookup"><span data-stu-id="7a23d-118">If the value cannot be completely determined by the enumeration entries, then the value is formatted as the integer value.</span></span> <span data-ttu-id="7a23d-119">En el siguiente ejemplo se muestra el uso del especificador de formato F.</span><span class="sxs-lookup"><span data-stu-id="7a23d-119">The following example illustrates the F format specifier.</span></span><br><br><span data-ttu-id="7a23d-120">[!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)] [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="7a23d-120">[!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)] [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]</span></span> |  
| <span data-ttu-id="7a23d-121">D o d</span><span class="sxs-lookup"><span data-stu-id="7a23d-121">D or d</span></span> | <span data-ttu-id="7a23d-122">Muestra la entrada de enumeración como valor entero en la representación más corta posible.</span><span class="sxs-lookup"><span data-stu-id="7a23d-122">Displays the enumeration entry as an integer value in the shortest representation possible.</span></span> <span data-ttu-id="7a23d-123">En el siguiente ejemplo se muestra el uso del especificador de formato D.</span><span class="sxs-lookup"><span data-stu-id="7a23d-123">The following example illustrates the D format specifier.</span></span><br><br><span data-ttu-id="7a23d-124">[!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)] [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="7a23d-124">[!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)] [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]</span></span> |  
| <span data-ttu-id="7a23d-125">X o x</span><span class="sxs-lookup"><span data-stu-id="7a23d-125">X or x</span></span> | <span data-ttu-id="7a23d-126">Muestra la entrada de enumeración como valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="7a23d-126">Displays the enumeration entry as a hexadecimal value.</span></span> <span data-ttu-id="7a23d-127">En caso necesario, el valor se representa con ceros iniciales para asegurarse de que tenga como mínimo ocho dígitos de longitud.</span><span class="sxs-lookup"><span data-stu-id="7a23d-127">The value is represented with leading zeros as necessary, to ensure that the value is a minimum eight digits in length.</span></span> <span data-ttu-id="7a23d-128">En el siguiente ejemplo se muestra el uso del especificador de formato X.</span><span class="sxs-lookup"><span data-stu-id="7a23d-128">The following example illustrates the X format specifier.</span></span><br /><br /> <span data-ttu-id="7a23d-129">[!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)] [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]</span><span class="sxs-lookup"><span data-stu-id="7a23d-129">[!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)] [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]</span></span> |  
  
## <a name="example"></a><span data-ttu-id="7a23d-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a23d-130">Example</span></span>  
 <span data-ttu-id="7a23d-131">En el ejemplo siguiente se define una enumeración denominada `Colors` que consta de tres entradas: `Red`, `Blue` y `Green`.</span><span class="sxs-lookup"><span data-stu-id="7a23d-131">The following example defines an enumeration called `Colors` that consists of three entries: `Red`, `Blue`, and `Green`.</span></span>  
  
 [!code-csharp[Formatting.Enum#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
 [!code-vb[Formatting.Enum#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]  
  
 <span data-ttu-id="7a23d-132">Una vez definida la enumeración, se puede declarar una instancia de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="7a23d-132">After the enumeration is defined, an instance can be declared in the following manner.</span></span>  
  
 [!code-csharp[Formatting.Enum#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
 [!code-vb[Formatting.Enum#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]  
  
 <span data-ttu-id="7a23d-133">Luego se puede usar el método `Color.ToString(System.String)` para mostrar el valor de enumeración de maneras diferentes, según el especificador de formato pasado.</span><span class="sxs-lookup"><span data-stu-id="7a23d-133">The `Color.ToString(System.String)` method can then be used to display the enumeration value in different ways, depending on the format specifier passed to it.</span></span>  
  
 [!code-csharp[Formatting.Enum#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
 [!code-vb[Formatting.Enum#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="7a23d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a23d-134">See Also</span></span>  
 [<span data-ttu-id="7a23d-135">Aplicación de formato a tipos</span><span class="sxs-lookup"><span data-stu-id="7a23d-135">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)
