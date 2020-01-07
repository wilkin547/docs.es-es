---
title: Collation
ms.date: 12/13/2019
description: Obtenga información sobre cómo crear una secuencia de intercalación personalizada.
ms.openlocfilehash: 0942ad4523a149ad74321cbe0f63021f53303579
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450289"
---
# <a name="collation"></a><span data-ttu-id="01fe3-103">Collation</span><span class="sxs-lookup"><span data-stu-id="01fe3-103">Collation</span></span>

<span data-ttu-id="01fe3-104">SQLite usa las secuencias de intercalación cuando se comparan valores de texto para determinar el orden y la igualdad.</span><span class="sxs-lookup"><span data-stu-id="01fe3-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="01fe3-105">Puede especificar la intercalación que se va a usar al crear columnas o por operación en consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="01fe3-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="01fe3-106">SQLite incluye tres secuencias de intercalación de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="01fe3-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="01fe3-107">Collation</span><span class="sxs-lookup"><span data-stu-id="01fe3-107">Collation</span></span> | <span data-ttu-id="01fe3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="01fe3-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="01fe3-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="01fe3-109">RTRIM</span></span>     | <span data-ttu-id="01fe3-110">Omite el espacio en blanco final</span><span class="sxs-lookup"><span data-stu-id="01fe3-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="01fe3-111">Nocase</span><span class="sxs-lookup"><span data-stu-id="01fe3-111">NOCASE</span></span>    | <span data-ttu-id="01fe3-112">No distingue entre mayúsculas y minúsculas para los caracteres ASCII A-Z</span><span class="sxs-lookup"><span data-stu-id="01fe3-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="01fe3-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="01fe3-113">BINARY</span></span>    | <span data-ttu-id="01fe3-114">Distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="01fe3-114">Case-sensitive.</span></span> <span data-ttu-id="01fe3-115">Compara los bytes directamente</span><span class="sxs-lookup"><span data-stu-id="01fe3-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="01fe3-116">Intercalación personalizada</span><span class="sxs-lookup"><span data-stu-id="01fe3-116">Custom collation</span></span>

<span data-ttu-id="01fe3-117">También puede definir sus propias secuencias de intercalación o invalidar las creadas mediante <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span><span class="sxs-lookup"><span data-stu-id="01fe3-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="01fe3-118">En el ejemplo siguiente se muestra cómo invalidar la intercalación nocase para admitir caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="01fe3-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="01fe3-119">El [código de ejemplo completo](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) está disponible en github.</span><span class="sxs-lookup"><span data-stu-id="01fe3-119">The [full sample code](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="01fe3-120">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="01fe3-120">Like operator</span></span>

<span data-ttu-id="01fe3-121">El operador LIKE de SQLite no respeta las intercalaciones.</span><span class="sxs-lookup"><span data-stu-id="01fe3-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="01fe3-122">La implementación predeterminada tiene la misma semántica que la intercalación nocase.</span><span class="sxs-lookup"><span data-stu-id="01fe3-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="01fe3-123">No distingue entre mayúsculas y minúsculas para los caracteres ASCII de la a a la Z.</span><span class="sxs-lookup"><span data-stu-id="01fe3-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="01fe3-124">Puede hacer que el operador LIKE distinga entre mayúsculas y minúsculas con la siguiente instrucción pragma:</span><span class="sxs-lookup"><span data-stu-id="01fe3-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 0
```

<span data-ttu-id="01fe3-125">Vea [funciones definidas por el usuario](user-defined-functions.md) para obtener más información sobre cómo invalidar la implementación del operador like.</span><span class="sxs-lookup"><span data-stu-id="01fe3-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="01fe3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="01fe3-126">See also</span></span>

* [<span data-ttu-id="01fe3-127">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="01fe3-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="01fe3-128">Sintaxis de SQL</span><span class="sxs-lookup"><span data-stu-id="01fe3-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
