---
title: Construcciones de referencia inversa en expresiones regulares
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
- backreferences
- constructs, backreference
- .NET Framework regular expressions, backreference constructs
- regular expressions, backreference constructs
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a884e70f542c2ed7ff63e39cb7eadedf0ef7b4d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="backreference-constructs-in-regular-expressions"></a><span data-ttu-id="a46b7-102">Construcciones de referencia inversa en expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="a46b7-102">Backreference Constructs in Regular Expressions</span></span>
<span data-ttu-id="a46b7-103">Las referencias inversas proporcionan una forma cómoda de identificar un carácter o subcadena repetidos dentro de una cadena.</span><span class="sxs-lookup"><span data-stu-id="a46b7-103">Backreferences provide a convenient way to identify a repeated character or substring within a string.</span></span> <span data-ttu-id="a46b7-104">Por ejemplo, si la cadena de entrada contiene varias apariciones de una subcadena arbitraria, puede buscar una coincidencia con la primera aparición con un grupo de captura y después usar una referencia inversa para buscar una coincidencia con las siguientes apariciones de la subcadena.</span><span class="sxs-lookup"><span data-stu-id="a46b7-104">For example, if the input string contains multiple occurrences of an arbitrary substring, you can match the first occurrence with a capturing group, and then use a backreference to match subsequent occurrences of the substring.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a46b7-105">Se usa una sintaxis independiente para hacer referencia a los grupos de captura con numeración y con nombre de las cadenas de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="a46b7-105">A separate syntax is used to refer to named and numbered capturing groups in replacement strings.</span></span> <span data-ttu-id="a46b7-106">Para obtener más información, consulta [Substitutions](substitutions-in-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a46b7-106">For more information, see [Substitutions](substitutions-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="a46b7-107">.NET define elementos del lenguaje independientes para hacer referencia a los grupos de captura con numeración y con nombre.</span><span class="sxs-lookup"><span data-stu-id="a46b7-107">.NET defines separate language elements to refer to numbered and named capturing groups.</span></span> <span data-ttu-id="a46b7-108">Para obtener más información acerca de grupos de captura, consulte [construcciones de agrupamiento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a46b7-108">For more information about capturing groups, see [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span></span>  
  
## <a name="numbered-backreferences"></a><span data-ttu-id="a46b7-109">Referencias inversas con numeración</span><span class="sxs-lookup"><span data-stu-id="a46b7-109">Numbered Backreferences</span></span>  
 <span data-ttu-id="a46b7-110">Una referencia inversa con numeración usa la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a46b7-110">A numbered backreference uses the following syntax:</span></span>  
  
 <span data-ttu-id="a46b7-111">`\` *número*</span><span class="sxs-lookup"><span data-stu-id="a46b7-111">`\` *number*</span></span>  
  
 <span data-ttu-id="a46b7-112">donde *número* es la posición ordinal del grupo de captura en la expresión regular.</span><span class="sxs-lookup"><span data-stu-id="a46b7-112">where *number* is the ordinal position of the capturing group in the regular expression.</span></span> <span data-ttu-id="a46b7-113">Por ejemplo, `\4` coincide con el contenido del cuarto grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="a46b7-113">For example, `\4` matches the contents of the fourth capturing group.</span></span> <span data-ttu-id="a46b7-114">Si *número* no es definido en el patrón de expresión regular, se produce un error de análisis y el motor de expresiones regulares produce una <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="a46b7-114">If *number* is not defined in the regular expression pattern, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="a46b7-115">Por ejemplo, la expresión regular `\b(\w+)\s\1` es válida, porque `(\w+)` es el primer y único grupo de captura de la expresión.</span><span class="sxs-lookup"><span data-stu-id="a46b7-115">For example, the regular expression `\b(\w+)\s\1` is valid, because `(\w+)` is the first and only capturing group in the expression.</span></span> <span data-ttu-id="a46b7-116">Por otro lado, `\b(\w+)\s\2` no es válida y produce una excepción de argumento porque no hay ningún grupo de captura con numeración `\2`.</span><span class="sxs-lookup"><span data-stu-id="a46b7-116">On the other hand, `\b(\w+)\s\2` is invalid and throws an argument exception, because there is no capturing group numbered `\2`.</span></span>  
  
 <span data-ttu-id="a46b7-117">Tenga en cuenta la ambigüedad existente entre códigos de escape octales (como `\16`) y `\` *número* referencias inversas que utilizan la misma notación.</span><span class="sxs-lookup"><span data-stu-id="a46b7-117">Note the ambiguity between octal escape codes (such as `\16`) and `\`*number* backreferences that use the same notation.</span></span> <span data-ttu-id="a46b7-118">Esta ambigüedad se resuelve de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="a46b7-118">This ambiguity is resolved as follows:</span></span>  
  
-   <span data-ttu-id="a46b7-119">Las expresiones `\1` a `\9` siempre se interpretan como referencias inversas y no como códigos octales.</span><span class="sxs-lookup"><span data-stu-id="a46b7-119">The expressions `\1` through `\9` are always interpreted as backreferences, and not as octal codes.</span></span>  
  
-   <span data-ttu-id="a46b7-120">Si el primer dígito de una expresión con varios dígitos es 8 o 9 (como `\80` o `\91`), la expresión se interpreta como un literal.</span><span class="sxs-lookup"><span data-stu-id="a46b7-120">If the first digit of a multidigit expression is 8 or 9 (such as `\80` or `\91`), the expression as interpreted as a literal.</span></span>  
  
-   <span data-ttu-id="a46b7-121">Las expresiones a partir de `\10` y superiores se consideran referencias inversas si hay una referencia inversa que se corresponda con ese número; en caso contrario, se interpretan como códigos octales.</span><span class="sxs-lookup"><span data-stu-id="a46b7-121">Expressions from `\10` and greater are considered backreferences if there is a backreference corresponding to that number; otherwise, they are interpreted as octal codes.</span></span>  
  
-   <span data-ttu-id="a46b7-122">Si una expresión regular contiene una referencia inversa a un número de grupo indefinido, se produce un error de análisis y el motor de expresiones regulares produce una <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="a46b7-122">If a regular expression contains a backreference to an undefined group number, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="a46b7-123">Si la ambigüedad constituye un problema, puede usar el `\k<` *nombre* `>` notación, que es ambiguo y no debe confundirse con códigos de caracteres octales.</span><span class="sxs-lookup"><span data-stu-id="a46b7-123">If the ambiguity is a problem, you can use the `\k<`*name*`>` notation, which is unambiguous and cannot be confused with octal character codes.</span></span> <span data-ttu-id="a46b7-124">De forma similar, los códigos hexadecimales como `\xdd` son inequívocos y no se pueden confundir con las referencias inversas.</span><span class="sxs-lookup"><span data-stu-id="a46b7-124">Similarly, hexadecimal codes such as `\xdd` are unambiguous and cannot be confused with backreferences.</span></span>  
  
 <span data-ttu-id="a46b7-125">En el ejemplo siguiente, se buscan caracteres de palabra duplicados en una cadena.</span><span class="sxs-lookup"><span data-stu-id="a46b7-125">The following example finds doubled word characters in a string.</span></span> <span data-ttu-id="a46b7-126">Define una expresión regular, `(\w)\1`, que consta de los siguientes elementos.</span><span class="sxs-lookup"><span data-stu-id="a46b7-126">It defines a regular expression, `(\w)\1`, which consists of the following elements.</span></span>  
  
|<span data-ttu-id="a46b7-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="a46b7-127">Element</span></span>|<span data-ttu-id="a46b7-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="a46b7-128">Description</span></span>|  
|-------------|-----------------|  
|`(\w)`|<span data-ttu-id="a46b7-129">Coincide con un carácter que se usa para formar palabras y se lo asigna al primer grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="a46b7-129">Match a word character and assign it to the first capturing group.</span></span>|  
|`\1`|<span data-ttu-id="a46b7-130">Coincide con el siguiente carácter que sea igual que el valor del primer grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="a46b7-130">Match the next character that is the same as the value of the first capturing group.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
 [!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]  
  
## <a name="named-backreferences"></a><span data-ttu-id="a46b7-131">Referencias inversas con nombre</span><span class="sxs-lookup"><span data-stu-id="a46b7-131">Named Backreferences</span></span>  
 <span data-ttu-id="a46b7-132">Una referencia inversa con nombre se define mediante la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="a46b7-132">A named backreference is defined by using the following syntax:</span></span>  
  
 <span data-ttu-id="a46b7-133">`\k<` *name* `>`</span><span class="sxs-lookup"><span data-stu-id="a46b7-133">`\k<` *name* `>`</span></span>  
  
 <span data-ttu-id="a46b7-134">O bien</span><span class="sxs-lookup"><span data-stu-id="a46b7-134">or:</span></span>  
  
 <span data-ttu-id="a46b7-135">`\k'` *nombre* `'`</span><span class="sxs-lookup"><span data-stu-id="a46b7-135">`\k'` *name* `'`</span></span>  
  
 <span data-ttu-id="a46b7-136">donde *nombre* es el nombre de un grupo de captura definido en el patrón de expresión regular.</span><span class="sxs-lookup"><span data-stu-id="a46b7-136">where *name* is the name of a capturing group defined in the regular expression pattern.</span></span> <span data-ttu-id="a46b7-137">Si *nombre* no es definido en el patrón de expresión regular, se produce un error de análisis y el motor de expresiones regulares produce una <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="a46b7-137">If *name* is not defined in the regular expression pattern, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="a46b7-138">En el ejemplo siguiente, se buscan caracteres de palabra duplicados en una cadena.</span><span class="sxs-lookup"><span data-stu-id="a46b7-138">The following example finds doubled word characters in a string.</span></span> <span data-ttu-id="a46b7-139">Define una expresión regular, `(?<char>\w)\k<char>`, que consta de los siguientes elementos.</span><span class="sxs-lookup"><span data-stu-id="a46b7-139">It defines a regular expression, `(?<char>\w)\k<char>`, which consists of the following elements.</span></span>  
  
|<span data-ttu-id="a46b7-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="a46b7-140">Element</span></span>|<span data-ttu-id="a46b7-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="a46b7-141">Description</span></span>|  
|-------------|-----------------|  
|`(?<char>\w)`|<span data-ttu-id="a46b7-142">Coincide con un carácter de palabra y asignarla a un grupo de captura denominado `char`.</span><span class="sxs-lookup"><span data-stu-id="a46b7-142">Match a word character and assign it to a capturing group named `char`.</span></span>|  
|`\k<char>`|<span data-ttu-id="a46b7-143">Coincide con el siguiente carácter que es el mismo que el valor de la `char` grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="a46b7-143">Match the next character that is the same as the value of the `char` capturing group.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
 [!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]  
  
 <span data-ttu-id="a46b7-144">Tenga en cuenta que *nombre* también puede ser la representación de cadena de un número.</span><span class="sxs-lookup"><span data-stu-id="a46b7-144">Note that *name* can also be the string representation of a number.</span></span> <span data-ttu-id="a46b7-145">Por ejemplo, en el ejemplo siguiente, se usa la expresión regular `(?<2>\w)\k<2>` para buscar caracteres de palabra duplicados en una cadena.</span><span class="sxs-lookup"><span data-stu-id="a46b7-145">For example, the following example uses the regular expression `(?<2>\w)\k<2>` to find doubled word characters in a string.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
 [!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]  
  
## <a name="what-backreferences-match"></a><span data-ttu-id="a46b7-146">Con qué coinciden las referencias inversas</span><span class="sxs-lookup"><span data-stu-id="a46b7-146">What Backreferences Match</span></span>  
 <span data-ttu-id="a46b7-147">Una referencia inversa constituye la definición más reciente de un grupo (la definición más inmediatamente a la izquierda, al coincidir de izquierda a derecha).</span><span class="sxs-lookup"><span data-stu-id="a46b7-147">A backreference refers to the most recent definition of a group (the definition most immediately to the left, when matching left to right).</span></span> <span data-ttu-id="a46b7-148">Cuando un grupo realiza varias capturas, una referencia inversa se refiere a la captura más reciente.</span><span class="sxs-lookup"><span data-stu-id="a46b7-148">When a group makes multiple captures, a backreference refers to the most recent capture.</span></span>  
  
 <span data-ttu-id="a46b7-149">En el ejemplo siguiente, se incluye un patrón de expresión regular, `(?<1>a)(?<1>\1b)*`, que redefine el grupo con nombre \1.</span><span class="sxs-lookup"><span data-stu-id="a46b7-149">The following example includes a regular expression pattern, `(?<1>a)(?<1>\1b)*`, which redefines the \1 named group.</span></span> <span data-ttu-id="a46b7-150">En la tabla siguiente, se describe cada patrón de la expresión regular.</span><span class="sxs-lookup"><span data-stu-id="a46b7-150">The following table describes each pattern in the regular expression.</span></span>  
  
|<span data-ttu-id="a46b7-151">Modelo</span><span class="sxs-lookup"><span data-stu-id="a46b7-151">Pattern</span></span>|<span data-ttu-id="a46b7-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="a46b7-152">Description</span></span>|  
|-------------|-----------------|  
|`(?<1>a)`|<span data-ttu-id="a46b7-153">Coincide con el carácter "a" y asignar el resultado al grupo de captura denominado `1`.</span><span class="sxs-lookup"><span data-stu-id="a46b7-153">Match the character "a" and assign the result to the capturing group named `1`.</span></span>|  
|`(?<1>\1b)*`|<span data-ttu-id="a46b7-154">Aparición de coincidencia 0 ó 1 del grupo de denominado `1` junto con un "b" y asigna el resultado al grupo de captura denominado `1`.</span><span class="sxs-lookup"><span data-stu-id="a46b7-154">Match 0 or 1 occurrence of the group named `1` along with a "b", and assign the result to the capturing group named `1`.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
 [!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]  
  
 <span data-ttu-id="a46b7-155">Al comparar la expresión regular con la cadena de entrada ("aababb"), el motor de expresiones regulares realiza las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="a46b7-155">In comparing the regular expression with the input string ("aababb"), the regular expression engine performs the following operations:</span></span>  
  
1.  <span data-ttu-id="a46b7-156">Comienza al principio de la cadena y hace que "a" coincida correctamente con la expresión `(?<1>a)`.</span><span class="sxs-lookup"><span data-stu-id="a46b7-156">It starts at the beginning of the string, and successfully matches "a" with the expression `(?<1>a)`.</span></span> <span data-ttu-id="a46b7-157">El valor de la `1` grupo es ahora "a".</span><span class="sxs-lookup"><span data-stu-id="a46b7-157">The value of the `1` group is now "a".</span></span>  
  
2.  <span data-ttu-id="a46b7-158">Se desplaza hasta el segundo carácter y hace que la cadena "ab" coincida correctamente con la expresión `\1b`, o "ab".</span><span class="sxs-lookup"><span data-stu-id="a46b7-158">It advances to the second character, and successfully matches the string "ab" with the expression `\1b`, or "ab".</span></span> <span data-ttu-id="a46b7-159">Después, asigna el resultado "ab" a `\1`.</span><span class="sxs-lookup"><span data-stu-id="a46b7-159">It then assigns the result, "ab" to `\1`.</span></span>  
  
3.  <span data-ttu-id="a46b7-160">Se desplaza hasta el cuarto carácter.</span><span class="sxs-lookup"><span data-stu-id="a46b7-160">It advances to the fourth character.</span></span> <span data-ttu-id="a46b7-161">La expresión `(?<1>\1b)` puede coincidir cero o más veces, así que la cadena "abb" coincide correctamente con la expresión `\1b`.</span><span class="sxs-lookup"><span data-stu-id="a46b7-161">The expression `(?<1>\1b)` is to be matched zero or more times, so it successfully matches the string "abb" with the expression `\1b`.</span></span> <span data-ttu-id="a46b7-162">Vuelve a asignar el resultado, "abb", a `\1`.</span><span class="sxs-lookup"><span data-stu-id="a46b7-162">It assigns the result, "abb", back to `\1`.</span></span>  
  
 <span data-ttu-id="a46b7-163">En este ejemplo, `*` es un cuantificador de bucle: se evalúa repetidas veces hasta que el motor de expresiones regulares no puede coincidir con el patrón que define.</span><span class="sxs-lookup"><span data-stu-id="a46b7-163">In this example, `*` is a looping quantifier -- it is evaluated repeatedly until the regular expression engine cannot match the pattern it defines.</span></span> <span data-ttu-id="a46b7-164">Los cuantificadores de bucle no borran las definiciones de grupo.</span><span class="sxs-lookup"><span data-stu-id="a46b7-164">Looping quantifiers do not clear group definitions.</span></span>  
  
 <span data-ttu-id="a46b7-165">Si un grupo no ha capturado ninguna subcadena, no se define una referencia inversa a ese grupo y no coincide nunca.</span><span class="sxs-lookup"><span data-stu-id="a46b7-165">If a group has not captured any substrings, a backreference to that group is undefined and never matches.</span></span> <span data-ttu-id="a46b7-166">Esto se muestra con el patrón de expresión regular `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, que se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="a46b7-166">This is illustrated by the regular expression pattern `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, which is defined as follows:</span></span>  
  
|<span data-ttu-id="a46b7-167">Modelo</span><span class="sxs-lookup"><span data-stu-id="a46b7-167">Pattern</span></span>|<span data-ttu-id="a46b7-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="a46b7-168">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="a46b7-169">Comienza la búsqueda de coincidencias en un límite de palabras.</span><span class="sxs-lookup"><span data-stu-id="a46b7-169">Begin the match on a word boundary.</span></span>|  
|`(\p{Lu}{2})`|<span data-ttu-id="a46b7-170">Coincide con dos letras mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="a46b7-170">Match two uppercase letters.</span></span> <span data-ttu-id="a46b7-171">Este es el primer grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="a46b7-171">This is the first capturing group.</span></span>|  
|`(\d{2})?`|<span data-ttu-id="a46b7-172">Coincide con una o ninguna aparición de dos dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="a46b7-172">Match zero or one occurrence of two decimal digits.</span></span> <span data-ttu-id="a46b7-173">Este es el segundo grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="a46b7-173">This is the second capturing group.</span></span>|  
|`(\p{Lu}{2})`|<span data-ttu-id="a46b7-174">Coincide con dos letras mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="a46b7-174">Match two uppercase letters.</span></span> <span data-ttu-id="a46b7-175">Éste es el tercer grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="a46b7-175">This is the third capturing group.</span></span>|  
|`\b`|<span data-ttu-id="a46b7-176">Finalizar la búsqueda de coincidencias en un límite de palabras.</span><span class="sxs-lookup"><span data-stu-id="a46b7-176">End the match on a word boundary.</span></span>|  
  
 <span data-ttu-id="a46b7-177">Una cadena de entrada puede coincidir con esta expresión regular aunque no estén presentes los dos dígitos decimales que define el segundo grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="a46b7-177">An input string can match this regular expression even if the two decimal digits that are defined by the second capturing group are not present.</span></span> <span data-ttu-id="a46b7-178">En el ejemplo siguiente, se muestra que, aunque la coincidencia es correcta, hay un grupo de captura vacío entre dos grupos de captura correctos.</span><span class="sxs-lookup"><span data-stu-id="a46b7-178">The following example shows that even though the match is successful, an empty capturing group is found between two successful capturing groups.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference5.cs#5)]
 [!code-vb[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="a46b7-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="a46b7-179">See Also</span></span>  
 [<span data-ttu-id="a46b7-180">Lenguaje de expresiones regulares: referencia rápida</span><span class="sxs-lookup"><span data-stu-id="a46b7-180">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
