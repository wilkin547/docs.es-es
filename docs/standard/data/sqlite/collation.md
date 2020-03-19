---
title: Intercalación
ms.date: 12/13/2019
description: Aprenda a crear una secuencia de intercalación personalizada.
ms.openlocfilehash: b93c82a4ace154b8293b05effa8f9e9294fa7708
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "79506546"
---
# <a name="collation"></a><span data-ttu-id="71582-103">Intercalación</span><span class="sxs-lookup"><span data-stu-id="71582-103">Collation</span></span>

<span data-ttu-id="71582-104">SQLite utiliza secuencias de intercalación al comparar valores DE TEXTO para determinar el orden y la igualdad.</span><span class="sxs-lookup"><span data-stu-id="71582-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="71582-105">Puede especificar qué intercalación se va a utilizar al crear columnas o por operación en consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="71582-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="71582-106">SQLite incluye tres secuencias de intercalación de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="71582-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="71582-107">Intercalación</span><span class="sxs-lookup"><span data-stu-id="71582-107">Collation</span></span> | <span data-ttu-id="71582-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="71582-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="71582-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="71582-109">RTRIM</span></span>     | <span data-ttu-id="71582-110">Ignora el espacio en blanco final</span><span class="sxs-lookup"><span data-stu-id="71582-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="71582-111">NOCASE</span><span class="sxs-lookup"><span data-stu-id="71582-111">NOCASE</span></span>    | <span data-ttu-id="71582-112">Sin distinción entre mayúsculas y minúsculas para caracteres ASCII A-Z</span><span class="sxs-lookup"><span data-stu-id="71582-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="71582-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="71582-113">BINARY</span></span>    | <span data-ttu-id="71582-114">Sensible a mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="71582-114">Case-sensitive.</span></span> <span data-ttu-id="71582-115">Compara bytes directamente</span><span class="sxs-lookup"><span data-stu-id="71582-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="71582-116">Intercalación personalizada</span><span class="sxs-lookup"><span data-stu-id="71582-116">Custom collation</span></span>

<span data-ttu-id="71582-117">También puede definir sus propias secuencias de intercalación o <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>invalidar las integradas mediante .</span><span class="sxs-lookup"><span data-stu-id="71582-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="71582-118">En el ejemplo siguiente se muestra cómo reemplazar la intercalación NOCASE para admitir caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="71582-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="71582-119">El [código de ejemplo completo](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) está disponible en GitHub.</span><span class="sxs-lookup"><span data-stu-id="71582-119">The [full sample code](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="71582-120">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="71582-120">Like operator</span></span>

<span data-ttu-id="71582-121">El operador LIKE de SQLite no respeta las intercalaciones.</span><span class="sxs-lookup"><span data-stu-id="71582-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="71582-122">La implementación predeterminada tiene la misma semántica que la intercalación NOCASE.</span><span class="sxs-lookup"><span data-stu-id="71582-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="71582-123">Solo distingue mayúsculas de minúsculas para los caracteres ASCII de la A a la Z.</span><span class="sxs-lookup"><span data-stu-id="71582-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="71582-124">Puede hacer que el operador LIKE distinta entre mayúsculas y minúsculas mediante la siguiente instrucción pragma:</span><span class="sxs-lookup"><span data-stu-id="71582-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 1
```

<span data-ttu-id="71582-125">Consulte [Funciones definidas por el usuario](user-defined-functions.md) para obtener más información sobre cómo reemplazar la implementación del operador LIKE.</span><span class="sxs-lookup"><span data-stu-id="71582-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="71582-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71582-126">See also</span></span>

* [<span data-ttu-id="71582-127">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="71582-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="71582-128">Sintaxis SQL</span><span class="sxs-lookup"><span data-stu-id="71582-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
