---
title: Nombres de identificador
description: Obtenga información sobre las reglas de los nombres de identificador válidos en el lenguaje de programación C#.
ms.date: 08/21/2018
ms.openlocfilehash: bef6e2ea285b5391af3350ae42a4105d140c6d1b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "77673373"
---
# <a name="identifier-names"></a><span data-ttu-id="64a39-103">Nombres de identificador</span><span class="sxs-lookup"><span data-stu-id="64a39-103">Identifier names</span></span>

<span data-ttu-id="64a39-104">Un **identificador** es el nombre que se asigna a un tipo (clase, interfaz, struct, delegado o enumeración), miembro, variable o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="64a39-104">An **identifier** is the name you assign to a type (class, interface, struct, delegate, or enum), member, variable, or namespace.</span></span> <span data-ttu-id="64a39-105">Los identificadores válidos deben seguir estas reglas:</span><span class="sxs-lookup"><span data-stu-id="64a39-105">Valid identifiers must follow these rules:</span></span>

- <span data-ttu-id="64a39-106">Los identificadores deben comenzar con una letra, o `_`.</span><span class="sxs-lookup"><span data-stu-id="64a39-106">Identifiers must start with a letter, or `_`.</span></span>
- <span data-ttu-id="64a39-107">Los identificadores pueden contener caracteres de letra Unicode, caracteres de dígito decimales, caracteres de conexión Unicode, caracteres de combinación Unicode o caracteres de formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="64a39-107">Identifiers may contain Unicode letter characters, decimal digit characters, Unicode connecting characters, Unicode combining characters, or Unicode formatting characters.</span></span> <span data-ttu-id="64a39-108">Para obtener más información sobre las categorías Unicode, vea la [base de datos de categorías Unicode](https://www.unicode.org/reports/tr44/).</span><span class="sxs-lookup"><span data-stu-id="64a39-108">For more information on Unicode categories, see the [Unicode Category Database](https://www.unicode.org/reports/tr44/).</span></span>
<span data-ttu-id="64a39-109">Puede declarar identificadores que coincidan con palabras clave de C# mediante el prefijo `@` en el identificador.</span><span class="sxs-lookup"><span data-stu-id="64a39-109">You can declare identifiers that match C# keywords by using the `@` prefix on the identifier.</span></span> <span data-ttu-id="64a39-110">`@` no forma parte del nombre de identificador.</span><span class="sxs-lookup"><span data-stu-id="64a39-110">The `@` is not part of the identifier name.</span></span> <span data-ttu-id="64a39-111">Por ejemplo, `@if` declara un identificador denominado `if`.</span><span class="sxs-lookup"><span data-stu-id="64a39-111">For example, `@if` declares an identifier named `if`.</span></span> <span data-ttu-id="64a39-112">Estos [identificadores textuales](../../language-reference/tokens/verbatim.md) son principalmente para la interoperabilidad con los identificadores declarados en otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="64a39-112">These [verbatim identifiers](../../language-reference/tokens/verbatim.md) are primarily for interoperability with identifiers declared in other languages.</span></span>

<span data-ttu-id="64a39-113">Para obtener una definición completa de identificadores válidos, vea el [tema Identificadores en la Especificación del lenguaje C#](../../../../_csharplang/spec/lexical-structure.md#identifiers).</span><span class="sxs-lookup"><span data-stu-id="64a39-113">For a complete definition of valid identifiers, see the [Identifiers topic in the C# Language Specification](../../../../_csharplang/spec/lexical-structure.md#identifiers).</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="64a39-114">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="64a39-114">Naming conventions</span></span>

<span data-ttu-id="64a39-115">Además de las reglas, hay una serie de [convenciones de nomenclatura](../../../standard/design-guidelines/naming-guidelines.md) de los identificadores que se usa en las API. de NET.</span><span class="sxs-lookup"><span data-stu-id="64a39-115">In addition to the rules, there are a number of identifier [naming conventions](../../../standard/design-guidelines/naming-guidelines.md) used throughout the .NET APIs.</span></span> <span data-ttu-id="64a39-116">Por convención, los programas de C# usan `PascalCase` para nombres de tipo, espacios de nombres y todos los miembros públicos.</span><span class="sxs-lookup"><span data-stu-id="64a39-116">By convention, C# programs use `PascalCase` for type names, namespaces, and all public members.</span></span> <span data-ttu-id="64a39-117">Además, son comunes las convenciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="64a39-117">In addition, the following conventions are common:</span></span>

- <span data-ttu-id="64a39-118">Los nombres de interfaz empiezan por una `I` mayúscula.</span><span class="sxs-lookup"><span data-stu-id="64a39-118">Interface names start with a capital `I`.</span></span>
- <span data-ttu-id="64a39-119">Los tipos de atributo terminan con la palabra `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="64a39-119">Attribute types end with the word `Attribute`.</span></span>
- <span data-ttu-id="64a39-120">Los tipos de enumeración usan un sustantivo singular para los que no son marcas y uno plural para los que sí.</span><span class="sxs-lookup"><span data-stu-id="64a39-120">Enum types use a singular noun for non-flags, and a plural noun for flags.</span></span>
- <span data-ttu-id="64a39-121">Los identificadores no deberían contener dos caracteres `_` consecutivos.</span><span class="sxs-lookup"><span data-stu-id="64a39-121">Identifiers should not contain two consecutive `_` characters.</span></span> <span data-ttu-id="64a39-122">Esos nombres están reservados para los identificadores generados por el compilador.</span><span class="sxs-lookup"><span data-stu-id="64a39-122">Those names are reserved for compiler generated identifiers.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="64a39-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="64a39-123">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="64a39-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="64a39-124">See also</span></span>

- [<span data-ttu-id="64a39-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="64a39-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="64a39-126">Dentro de un programa de C#</span><span class="sxs-lookup"><span data-stu-id="64a39-126">Inside a C# Program</span></span>](./index.md)
- [<span data-ttu-id="64a39-127">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="64a39-127">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="64a39-128">Clases</span><span class="sxs-lookup"><span data-stu-id="64a39-128">Classes</span></span>](../classes-and-structs/classes.md)
- [<span data-ttu-id="64a39-129">Tipos de estructura</span><span class="sxs-lookup"><span data-stu-id="64a39-129">Structure types</span></span>](../../language-reference/builtin-types/struct.md)
- [<span data-ttu-id="64a39-130">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="64a39-130">Namespaces</span></span>](../namespaces/index.md)
- [<span data-ttu-id="64a39-131">Interfaces</span><span class="sxs-lookup"><span data-stu-id="64a39-131">Interfaces</span></span>](../interfaces/index.md)
- [<span data-ttu-id="64a39-132">Delegados</span><span class="sxs-lookup"><span data-stu-id="64a39-132">Delegates</span></span>](../delegates/index.md)
