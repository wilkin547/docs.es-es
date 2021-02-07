---
description: 'Más información sobre: construir tipos (Entity SQL)'
title: Tipos de constructores (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41fa7bde-8d20-4a3f-a3d2-fb791e128010
ms.openlocfilehash: 5963c34ffd8e9273d400cc16ba93f72ded2ede46
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724848"
---
# <a name="constructing-types-entity-sql"></a><span data-ttu-id="ca543-103">Tipos de constructores (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ca543-103">Constructing Types (Entity SQL)</span></span>

<!-- markdownlint-disable DOCSMD001 -->
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="ca543-104">proporciona tres tipos de constructores: constructores Row, constructores de tipos con nombre y constructores de colección.</span><span class="sxs-lookup"><span data-stu-id="ca543-104">provides three kinds of constructors: row constructors, named type constructors, and collection constructors.</span></span>

## <a name="row-constructors"></a><span data-ttu-id="ca543-105">Constructores ROW</span><span class="sxs-lookup"><span data-stu-id="ca543-105">Row Constructors</span></span>

<span data-ttu-id="ca543-106">Los constructores ROW de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se usan para crear registros anónimos con tipo estructural de uno o más valores.</span><span class="sxs-lookup"><span data-stu-id="ca543-106">You use row constructors in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="ca543-107">El tipo de resultado de un constructor ROW es un tipo de fila cuyos tipos de campo corresponden a los tipos de los valores que se utilizaron para crear la fila.</span><span class="sxs-lookup"><span data-stu-id="ca543-107">The result type of a row constructor is a row type whose field types correspond to the types of the values used to construct the row.</span></span> <span data-ttu-id="ca543-108">Por ejemplo, la expresión siguiente crea un valor de tipo `Record(a int, b string, c int)` :</span><span class="sxs-lookup"><span data-stu-id="ca543-108">For example, the following expression constructs a value of type `Record(a int, b string, c int)`:</span></span>

`ROW(1 AS a, "abc" AS b, a + 34 AS c)`

<span data-ttu-id="ca543-109">Si no proporciona un alias para una expresión en un constructor ROW, Entity Framework intentará generar uno.</span><span class="sxs-lookup"><span data-stu-id="ca543-109">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="ca543-110">Para obtener más información, vea la sección "reglas de alias" en [identificadores](identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ca543-110">For more information, see the "Aliasing Rules" section in [Identifiers](identifiers-entity-sql.md).</span></span>

<span data-ttu-id="ca543-111">Las reglas siguientes se aplican a expresiones que usan alias en un constructor ROW:</span><span class="sxs-lookup"><span data-stu-id="ca543-111">The following rules apply to expression aliasing in a row constructor:</span></span>

- <span data-ttu-id="ca543-112">Las expresiones en un constructor ROW no pueden hacer referencia a otros alias del mismo constructor.</span><span class="sxs-lookup"><span data-stu-id="ca543-112">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>
- <span data-ttu-id="ca543-113">Dos expresiones en el mismo constructor ROW no pueden tener el mismo alias.</span><span class="sxs-lookup"><span data-stu-id="ca543-113">Two expressions in the same row constructor cannot have the same alias.</span></span>

<span data-ttu-id="ca543-114">Para obtener más información sobre los constructores de filas, vea [Row](row-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ca543-114">For more information about row constructors, see [ROW](row-entity-sql.md).</span></span>

## <a name="collection-constructors"></a><span data-ttu-id="ca543-115">Constructores de colecciones</span><span class="sxs-lookup"><span data-stu-id="ca543-115">Collection Constructors</span></span>

<span data-ttu-id="ca543-116">Los constructores de colecciones de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se usan para crear una instancia de un elemento multiset a partir de una lista de valores.</span><span class="sxs-lookup"><span data-stu-id="ca543-116">You use collection constructors in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="ca543-117">Todos los valores del constructor deben ser del tipo `T` mutuamente compatible y el constructor genera una colección de tipo `Multiset<T>`.</span><span class="sxs-lookup"><span data-stu-id="ca543-117">All the values in the constructor must be of mutually compatible type `T`, and the constructor produces a collection of type `Multiset<T>`.</span></span> <span data-ttu-id="ca543-118">Por ejemplo, la expresión siguiente crea una colección de enteros:</span><span class="sxs-lookup"><span data-stu-id="ca543-118">For example, the following expression creates a collection of integers:</span></span>

`Multiset(1, 2, 3)`

`{1, 2, 3}`

<span data-ttu-id="ca543-119">No se permiten los constructores multiset vacíos porque no se puede determinar el tipo de los elementos.</span><span class="sxs-lookup"><span data-stu-id="ca543-119">Empty multiset constructors are not allowed because the type of the elements cannot be determined.</span></span> <span data-ttu-id="ca543-120">Lo siguiente no es válido:</span><span class="sxs-lookup"><span data-stu-id="ca543-120">The following is not valid:</span></span>

`multiset() {}`

<span data-ttu-id="ca543-121">Para obtener más información, vea [MultiSet](multiset-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ca543-121">For more information, see [MULTISET](multiset-entity-sql.md).</span></span>

## <a name="named-type-constructors-namedtype-initializers"></a><span data-ttu-id="ca543-122">Constructores de tipos con nombre (inicializadores NamedType)</span><span class="sxs-lookup"><span data-stu-id="ca543-122">Named Type Constructors (NamedType Initializers)</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="ca543-123">permite a los constructores de tipos (inicializadores) crear instancias de tipos complejos con nombre y de tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="ca543-123">allows type constructors (initializers) to create instances of named complex types and entity types.</span></span> <span data-ttu-id="ca543-124">Por ejemplo, la expresión siguiente crea una instancia de un tipo `Person`.</span><span class="sxs-lookup"><span data-stu-id="ca543-124">For example, the following expression creates an instance of a `Person` type.</span></span>

`Person("abc", 12)`

<span data-ttu-id="ca543-125">La expresión siguiente crea una instancia de un tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="ca543-125">The following expression creates an instance of a complex type.</span></span>

`MyModel.ZipCode(‘98118’, ‘4567’)`

<span data-ttu-id="ca543-126">La expresión siguiente crea una instancia de un tipo complejo anidado.</span><span class="sxs-lookup"><span data-stu-id="ca543-126">The following expression creates an instance of a nested complex type.</span></span>

`MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`

<span data-ttu-id="ca543-127">La expresión siguiente crea una instancia de una entidad con un tipo complejo anidado.</span><span class="sxs-lookup"><span data-stu-id="ca543-127">The following expression creates an instance of an entity with a nested complex type.</span></span>

`MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`

<span data-ttu-id="ca543-128">En el ejemplo siguiente se muestra cómo inicializar una propiedad de un tipo complejo en NULL.</span><span class="sxs-lookup"><span data-stu-id="ca543-128">The following example shows how to initialize a property of a complex type to null.</span></span> `MyModel.ZipCode(‘98118’, null)`

<span data-ttu-id="ca543-129">Los argumentos del constructor se supone que están en el mismo orden que en la declaración de los atributos del tipo.</span><span class="sxs-lookup"><span data-stu-id="ca543-129">The arguments to the constructor are assumed to be in the same order as the declaration of the attributes of the type.</span></span>

<span data-ttu-id="ca543-130">Para obtener más información, vea [constructor de tipo con nombre](named-type-constructor-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ca543-130">For more information, see [Named Type Constructor](named-type-constructor-entity-sql.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ca543-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca543-131">See also</span></span>

- [<span data-ttu-id="ca543-132">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ca543-132">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="ca543-133">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ca543-133">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="ca543-134">Sistema de tipos</span><span class="sxs-lookup"><span data-stu-id="ca543-134">Type System</span></span>](type-system-entity-sql.md)
