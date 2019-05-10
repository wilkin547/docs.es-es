---
title: Procedimiento Declare una constante (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.constant
helpviewer_keywords:
- Integer data type [Visual Basic], declaring constants
- Single data type [Visual Basic], declaring constants
- Const statement [Visual Basic], declaring constants
- procedures [Visual Basic], declaration
- data types [Visual Basic], constants
- Long data type [Visual Basic], declaring constants
- Visual Basic code, declaring variables and constants
- Double data type [Visual Basic], declaring constants
- Boolean data type [Visual Basic], declaring constants
- modules, declaring constants
- Byte data type [Visual Basic], declaring constants
- constants [Visual Basic], declaring
- Date data type [Visual Basic], declaring constants
- String data type [Visual Basic], declaring constants
- declaring constants [Visual Basic], const keyword
- Currency data type [Visual Basic], declaring constants and variants
- module-level constants and variables
- Object data type [Visual Basic], declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
ms.openlocfilehash: b84afe4e354d4029bc61ba67bc93bd36a3430de4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610597"
---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="97276-102">Procedimiento Declare una constante (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97276-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="97276-103">Usa el `Const` instrucción declare una constante y establezca su valor.</span><span class="sxs-lookup"><span data-stu-id="97276-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="97276-104">Al declarar una constante, asigna un nombre descriptivo a un valor.</span><span class="sxs-lookup"><span data-stu-id="97276-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="97276-105">Una vez que se declara una constante, no se puede modificar o asignar un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="97276-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="97276-106">Declare una constante dentro de un procedimiento o en la sección de declaraciones de un módulo, clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="97276-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="97276-107">Constantes de nivel de la estructura o clase son `Private` de forma predeterminada, pero también pueden declararse como `Public`, `Friend`, `Protected`, o `Protected Friend` para el nivel adecuado de acceso al código.</span><span class="sxs-lookup"><span data-stu-id="97276-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="97276-108">La constante debe tener un nombre simbólico válido (las reglas son las mismas que para crear nombres de variable) y una expresión que se compone de numérico o cadena constantes y operadores (pero no hay llamadas de función).</span><span class="sxs-lookup"><span data-stu-id="97276-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="97276-109">Para declarar una constante</span><span class="sxs-lookup"><span data-stu-id="97276-109">To declare a constant</span></span>  
  
- <span data-ttu-id="97276-110">Escribir una declaración que incluye un especificador de acceso, el `Const` palabra clave y una expresión, como en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="97276-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     <span data-ttu-id="97276-111">Cuando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) es `Off` y [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) es `On`, debe declarar una constante de forma explícita mediante la especificación de un tipo de datos (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, o `String`).</span><span class="sxs-lookup"><span data-stu-id="97276-111">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="97276-112">Cuando `Option Infer` es `On` o `Option Strict` es `Off`, puede declarar una constante sin especificar un tipo de datos con un `As` cláusula.</span><span class="sxs-lookup"><span data-stu-id="97276-112">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="97276-113">El compilador determina el tipo de la constante del tipo de la expresión.</span><span class="sxs-lookup"><span data-stu-id="97276-113">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="97276-114">Para obtener más información, consulte [constante y los tipos de datos Literal](constant-and-literal-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="97276-114">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="97276-115">Para declarar una constante que tiene un tipo de datos explícitamente establecidos</span><span class="sxs-lookup"><span data-stu-id="97276-115">To declare a constant that has an explicitly stated data type</span></span>  
  
- <span data-ttu-id="97276-116">Escribir una declaración que incluya la `As` palabra clave y un explícitas tipo de datos, como en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="97276-116">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     <span data-ttu-id="97276-117">Puede declarar varias constantes en una sola línea, aunque el código es más legible si declara solamente una constante por línea.</span><span class="sxs-lookup"><span data-stu-id="97276-117">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="97276-118">Si declara varias constantes en una sola línea, debe tener el mismo nivel de acceso (`Public`, `Private`, `Friend`, `Protected`, o `Protected Friend`).</span><span class="sxs-lookup"><span data-stu-id="97276-118">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="97276-119">Para declarar varias constantes en una sola línea</span><span class="sxs-lookup"><span data-stu-id="97276-119">To declare multiple constants on a single line</span></span>  
  
- <span data-ttu-id="97276-120">Separe las declaraciones con una coma y un espacio, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="97276-120">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="97276-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="97276-121">See also</span></span>

- [<span data-ttu-id="97276-122">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="97276-122">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="97276-123">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="97276-123">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="97276-124">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="97276-124">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="97276-125">Cómo: Declarar una constante</span><span class="sxs-lookup"><span data-stu-id="97276-125">How to: Declare A Constant</span></span>](how-to-declare-a-constant.md)
- [<span data-ttu-id="97276-126">Constantes definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="97276-126">User-Defined Constants</span></span>](user-defined-constants.md)
- [<span data-ttu-id="97276-127">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="97276-127">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="97276-128">Cómo: Agrupar valores de constantes relacionadas</span><span class="sxs-lookup"><span data-stu-id="97276-128">How to: Group Related Constant Values Together</span></span>](how-to-group-related-constant-values-together.md)
- [<span data-ttu-id="97276-129">Información general sobre las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="97276-129">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="97276-130">Cómo: Declarar enumeraciones</span><span class="sxs-lookup"><span data-stu-id="97276-130">How to: Declare Enumerations</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="97276-131">Cómo: Hacer referencia a un miembro de enumeración</span><span class="sxs-lookup"><span data-stu-id="97276-131">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="97276-132">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="97276-132">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="97276-133">Cómo: Recorrer en iteración una enumeración</span><span class="sxs-lookup"><span data-stu-id="97276-133">How to: Iterate Through An Enumeration</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="97276-134">Cómo: Determinar la cadena asociada con un valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="97276-134">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="97276-135">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="97276-135">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)

- [<span data-ttu-id="97276-136">Información general sobre las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="97276-136">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="97276-137">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="97276-137">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="97276-138">Cómo: Declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="97276-138">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="97276-139">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="97276-139">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="97276-140">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="97276-140">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="97276-141">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="97276-141">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
