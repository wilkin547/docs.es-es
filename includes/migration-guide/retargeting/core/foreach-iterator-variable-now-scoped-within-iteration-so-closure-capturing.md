---
ms.openlocfilehash: 9a2d6a25a8ab1b8bf65b947557802e0805a7f826
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617275"
---
### <a name="foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a><span data-ttu-id="9fa2b-101">La variable de iterador Foreach ahora tiene como ámbito la iteración, por lo que la semántica de captura de clausura es diferente (en C#5)</span><span class="sxs-lookup"><span data-stu-id="9fa2b-101">Foreach iterator variable is now scoped within the iteration, so closure capturing semantics are different (in C#5)</span></span>

#### <a name="details"></a><span data-ttu-id="9fa2b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="9fa2b-102">Details</span></span>

<span data-ttu-id="9fa2b-103">A partir de C#5 (Visual Studio 2012), las variables de iterador `foreach` tienen como ámbito la iteración.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-103">Beginning with C# 5 (Visual Studio 2012), `foreach` iterator variables are scoped within the iteration.</span></span> <span data-ttu-id="9fa2b-104">Esto puede provocar interrupciones si el código dependía anteriormente de que las variables no se incluyeran en la clausura de `foreach`.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-104">This can cause breaks if code was previously depending on the variables to not be included in the `foreach`'s closure.</span></span> <span data-ttu-id="9fa2b-105">El síntoma de este cambio es que una variable de iterador que se pasa a un delegado se trata como el valor que tiene en el momento de creación del delegado, en lugar de como el valor que tiene en el momento de invocarlo.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-105">The symptom of this change is that an iterator variable passed to a delegate is treated as the value it has at the time the delegate is created, rather than the value it has at the time the delegate is invoked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9fa2b-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="9fa2b-106">Suggestion</span></span>

<span data-ttu-id="9fa2b-107">Lo ideal sería actualizar el código para que espere el nuevo comportamiento del compilador.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-107">Ideally, code should be updated to expect the new compiler behavior.</span></span> <span data-ttu-id="9fa2b-108">Si es necesario usar la semántica anterior, es posible reemplazar la variable de iterador por una variable independiente colocada de forma explícita fuera del ámbito del bucle.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-108">If the old semantics are required, the iterator variable can be replaced with a separate variable which is explicitly placed outside of the loop's scope.</span></span>

| <span data-ttu-id="9fa2b-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="9fa2b-109">Name</span></span>    | <span data-ttu-id="9fa2b-110">Valor</span><span class="sxs-lookup"><span data-stu-id="9fa2b-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9fa2b-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="9fa2b-111">Scope</span></span>   | <span data-ttu-id="9fa2b-112">Major</span><span class="sxs-lookup"><span data-stu-id="9fa2b-112">Major</span></span>       |
| <span data-ttu-id="9fa2b-113">Versión</span><span class="sxs-lookup"><span data-stu-id="9fa2b-113">Version</span></span> | <span data-ttu-id="9fa2b-114">4.5</span><span class="sxs-lookup"><span data-stu-id="9fa2b-114">4.5</span></span>         |
| <span data-ttu-id="9fa2b-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="9fa2b-115">Type</span></span>    | <span data-ttu-id="9fa2b-116">Redestinación</span><span class="sxs-lookup"><span data-stu-id="9fa2b-116">Retargeting</span></span> |
