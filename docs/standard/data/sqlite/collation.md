---
title: Collation
ms.date: 12/13/2019
description: Obtenga información sobre cómo crear una secuencia de intercalación personalizada.
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242977"
---
# <a name="collation"></a><span data-ttu-id="a4a22-103">Collation</span><span class="sxs-lookup"><span data-stu-id="a4a22-103">Collation</span></span>

<span data-ttu-id="a4a22-104">SQLite usa las secuencias de intercalación al comparar valores de texto para determinar el orden y la igualdad.</span><span class="sxs-lookup"><span data-stu-id="a4a22-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="a4a22-105">Puede especificar la intercalación que se va a usar al crear columnas o por operación en consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="a4a22-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="a4a22-106">SQLite incluye tres secuencias de intercalación de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a4a22-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="a4a22-107">Collation</span><span class="sxs-lookup"><span data-stu-id="a4a22-107">Collation</span></span> | <span data-ttu-id="a4a22-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4a22-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="a4a22-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="a4a22-109">RTRIM</span></span>     | <span data-ttu-id="a4a22-110">Ignora los espacios en blanco finales</span><span class="sxs-lookup"><span data-stu-id="a4a22-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="a4a22-111">NOCASE</span><span class="sxs-lookup"><span data-stu-id="a4a22-111">NOCASE</span></span>    | <span data-ttu-id="a4a22-112">No distingue mayúsculas de minúsculas para los caracteres ASCII A-Z</span><span class="sxs-lookup"><span data-stu-id="a4a22-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="a4a22-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="a4a22-113">BINARY</span></span>    | <span data-ttu-id="a4a22-114">Distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a4a22-114">Case-sensitive.</span></span> <span data-ttu-id="a4a22-115">Compara los bytes directamente</span><span class="sxs-lookup"><span data-stu-id="a4a22-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="a4a22-116">Intercalación personalizada</span><span class="sxs-lookup"><span data-stu-id="a4a22-116">Custom collation</span></span>

<span data-ttu-id="a4a22-117">También puede definir secuencias de intercalación propias o invalidar las creadas mediante <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4a22-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="a4a22-118">En el ejemplo siguiente se muestra cómo invalidar la intercalación NOCASE para admitir caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="a4a22-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="a4a22-119">El [ejemplo de código completo](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) está disponible en GitHub.</span><span class="sxs-lookup"><span data-stu-id="a4a22-119">The [full sample code](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="a4a22-120">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="a4a22-120">Like operator</span></span>

<span data-ttu-id="a4a22-121">El operador LIKE de SQLite no respeta las intercalaciones.</span><span class="sxs-lookup"><span data-stu-id="a4a22-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="a4a22-122">La implementación predeterminada tiene la misma semántica que la intercalación NOCASE.</span><span class="sxs-lookup"><span data-stu-id="a4a22-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="a4a22-123">No distingue mayúsculas de minúsculas para los caracteres ASCII de la A a la Z.</span><span class="sxs-lookup"><span data-stu-id="a4a22-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="a4a22-124">Puede hacer que el operador LIKE distinga mayúsculas de minúsculas con la siguiente instrucción pragma:</span><span class="sxs-lookup"><span data-stu-id="a4a22-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 1
```

<span data-ttu-id="a4a22-125">Vea [Funciones definidas por el usuario](user-defined-functions.md) para obtener más información sobre cómo invalidar la implementación del operador LIKE.</span><span class="sxs-lookup"><span data-stu-id="a4a22-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4a22-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4a22-126">See also</span></span>

* [<span data-ttu-id="a4a22-127">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="a4a22-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="a4a22-128">Sintaxis de SQL</span><span class="sxs-lookup"><span data-stu-id="a4a22-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
