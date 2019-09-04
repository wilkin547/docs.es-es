---
title: Tipos de constructores (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41fa7bde-8d20-4a3f-a3d2-fb791e128010
ms.openlocfilehash: 7113aaf1c2caa982a8ab4751928856c1271570cb
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251117"
---
# <a name="constructing-types-entity-sql"></a><span data-ttu-id="551c1-102">Tipos de constructores (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="551c1-102">Constructing Types (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="551c1-103">proporciona tres tipos de constructores: constructores Row, constructores de tipos con nombre y constructores de colección.</span><span class="sxs-lookup"><span data-stu-id="551c1-103">provides three kinds of constructors: row constructors, named type constructors, and collection constructors.</span></span>  
  
## <a name="row-constructors"></a><span data-ttu-id="551c1-104">Constructores ROW</span><span class="sxs-lookup"><span data-stu-id="551c1-104">Row Constructors</span></span>  
 <span data-ttu-id="551c1-105">Los constructores ROW de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se usan para crear registros anónimos con tipo estructural de uno o más valores.</span><span class="sxs-lookup"><span data-stu-id="551c1-105">You use row constructors in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="551c1-106">El tipo de resultado de un constructor ROW es un tipo de fila cuyos tipos de campo corresponden a los tipos de los valores que se utilizaron para crear la fila.</span><span class="sxs-lookup"><span data-stu-id="551c1-106">The result type of a row constructor is a row type whose field types correspond to the types of the values used to construct the row.</span></span> <span data-ttu-id="551c1-107">Por ejemplo, la expresión siguiente crea un valor de tipo `Record(a int, b string, c int)`:</span><span class="sxs-lookup"><span data-stu-id="551c1-107">For example, the following expression constructs a value of type `Record(a int, b string, c int)`:</span></span>  
  
 `ROW(1 AS a, "abc" AS b, a + 34 AS c)`  
  
 <span data-ttu-id="551c1-108">Si no proporciona un alias para una expresión en un constructor ROW, Entity Framework intentará generar uno.</span><span class="sxs-lookup"><span data-stu-id="551c1-108">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="551c1-109">Para obtener más información, vea la sección "reglas de alias" en [identificadores](identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="551c1-109">For more information, see the "Aliasing Rules" section in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="551c1-110">Las reglas siguientes se aplican a expresiones que usan alias en un constructor ROW:</span><span class="sxs-lookup"><span data-stu-id="551c1-110">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
- <span data-ttu-id="551c1-111">Las expresiones en un constructor ROW no pueden hacer referencia a otros alias del mismo constructor.</span><span class="sxs-lookup"><span data-stu-id="551c1-111">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
- <span data-ttu-id="551c1-112">Dos expresiones en el mismo constructor ROW no pueden tener el mismo alias.</span><span class="sxs-lookup"><span data-stu-id="551c1-112">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="551c1-113">Para obtener más información sobre los constructores de filas, vea [Row](row-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="551c1-113">For more information about row constructors, see [ROW](row-entity-sql.md).</span></span>  
  
## <a name="collection-constructors"></a><span data-ttu-id="551c1-114">Constructores de colecciones</span><span class="sxs-lookup"><span data-stu-id="551c1-114">Collection Constructors</span></span>  
 <span data-ttu-id="551c1-115">Los constructores de colecciones de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se usan para crear una instancia de un elemento multiset a partir de una lista de valores.</span><span class="sxs-lookup"><span data-stu-id="551c1-115">You use collection constructors in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="551c1-116">Todos los valores del constructor deben ser del tipo `T` mutuamente compatible y el constructor genera una colección de tipo `Multiset<T>`.</span><span class="sxs-lookup"><span data-stu-id="551c1-116">All the values in the constructor must be of mutually compatible type `T`, and the constructor produces a collection of type `Multiset<T>`.</span></span> <span data-ttu-id="551c1-117">Por ejemplo, la expresión siguiente crea una colección de enteros:</span><span class="sxs-lookup"><span data-stu-id="551c1-117">For example, the following expression creates a collection of integers:</span></span>  
  
 `Multiset(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
 <span data-ttu-id="551c1-118">No se permiten los constructores multiset vacíos porque no se puede determinar el tipo de los elementos.</span><span class="sxs-lookup"><span data-stu-id="551c1-118">Empty multiset constructors are not allowed because the type of the elements cannot be determined.</span></span> <span data-ttu-id="551c1-119">Lo siguiente no es válido:</span><span class="sxs-lookup"><span data-stu-id="551c1-119">The following is not valid:</span></span>  
  
 `multiset() {}`  
  
 <span data-ttu-id="551c1-120">Para obtener más información, vea [MultiSet](multiset-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="551c1-120">For more information, see [MULTISET](multiset-entity-sql.md).</span></span>  
  
## <a name="named-type-constructors-namedtype-initializers"></a><span data-ttu-id="551c1-121">Constructores de tipos con nombre (inicializadores NamedType)</span><span class="sxs-lookup"><span data-stu-id="551c1-121">Named Type Constructors (NamedType Initializers)</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="551c1-122">permite a los constructores de tipos (inicializadores) crear instancias de tipos complejos con nombre y de tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="551c1-122">allows type constructors (initializers) to create instances of named complex types and entity types.</span></span> <span data-ttu-id="551c1-123">Por ejemplo, la expresión siguiente crea una instancia de un tipo `Person`.</span><span class="sxs-lookup"><span data-stu-id="551c1-123">For example, the following expression creates an instance of a `Person` type.</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="551c1-124">La expresión siguiente crea una instancia de un tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="551c1-124">The following expression creates an instance of a complex type.</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="551c1-125">La expresión siguiente crea una instancia de un tipo complejo anidado.</span><span class="sxs-lookup"><span data-stu-id="551c1-125">The following expression creates an instance of a nested complex type.</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="551c1-126">La expresión siguiente crea una instancia de una entidad con un tipo complejo anidado.</span><span class="sxs-lookup"><span data-stu-id="551c1-126">The following expression creates an instance of an entity with a nested complex type.</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="551c1-127">En el ejemplo siguiente se muestra cómo inicializar una propiedad de un tipo complejo en NULL.</span><span class="sxs-lookup"><span data-stu-id="551c1-127">The following example shows how to initialize a property of a complex type to null.</span></span> `MyModel.ZipCode(‘98118’, null)`  
  
 <span data-ttu-id="551c1-128">Los argumentos del constructor se supone que están en el mismo orden que en la declaración de los atributos del tipo.</span><span class="sxs-lookup"><span data-stu-id="551c1-128">The arguments to the constructor are assumed to be in the same order as the declaration of the attributes of the type.</span></span>  
  
 <span data-ttu-id="551c1-129">Para obtener más información, vea [constructor de tipo con nombre](named-type-constructor-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="551c1-129">For more information, see [Named Type Constructor](named-type-constructor-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="551c1-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="551c1-130">See also</span></span>

- [<span data-ttu-id="551c1-131">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="551c1-131">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="551c1-132">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="551c1-132">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="551c1-133">Sistema de tipos</span><span class="sxs-lookup"><span data-stu-id="551c1-133">Type System</span></span>](type-system-entity-sql.md)
