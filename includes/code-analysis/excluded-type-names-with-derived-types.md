---
ms.openlocfilehash: 150882f3e4c9ff7abe811e09da94b8141de75778
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "97366836"
---
### <a name="exclude-specific-types-and-their-derived-types"></a><span data-ttu-id="a8bb3-101">Excluir tipos específicos y sus tipos derivados</span><span class="sxs-lookup"><span data-stu-id="a8bb3-101">Exclude specific types and their derived types</span></span>

<span data-ttu-id="a8bb3-102">Puede excluir tipos específicos y sus tipos derivados del análisis.</span><span class="sxs-lookup"><span data-stu-id="a8bb3-102">You can exclude specific types and their derived types from analysis.</span></span> <span data-ttu-id="a8bb3-103">Por ejemplo, para especificar que la regla no se debe ejecutar en ningún método de los tipos denominados `MyType` y sus tipos derivados, agregue el siguiente par clave-valor a un archivo *. editorconfig* en el proyecto:</span><span class="sxs-lookup"><span data-stu-id="a8bb3-103">For example, to specify that the rule should not run on any methods within types named `MyType` and their derived types, add the following key-value pair to an *.editorconfig* file in your project:</span></span>

```ini
dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType
```

<span data-ttu-id="a8bb3-104">Formatos de nombre de símbolo permitidos en el valor de opción (separados por `|` ):</span><span class="sxs-lookup"><span data-stu-id="a8bb3-104">Allowed symbol name formats in the option value (separated by `|`):</span></span>

- <span data-ttu-id="a8bb3-105">Solo nombre de tipo (incluye todos los tipos con el nombre, sin tener en cuenta el tipo o espacio de nombres contenedor).</span><span class="sxs-lookup"><span data-stu-id="a8bb3-105">Type name only (includes all types with the name, regardless of the containing type or namespace)..</span></span>
- <span data-ttu-id="a8bb3-106">Nombres completos en el [formato de identificador de documentación](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings)del símbolo, con un `T:` prefijo opcional.</span><span class="sxs-lookup"><span data-stu-id="a8bb3-106">Fully qualified names in the symbol's [documentation ID format](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings), with an optional `T:` prefix.</span></span>

<span data-ttu-id="a8bb3-107">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a8bb3-107">Examples:</span></span>

| <span data-ttu-id="a8bb3-108">Valor de la opción</span><span class="sxs-lookup"><span data-stu-id="a8bb3-108">Option Value</span></span> | <span data-ttu-id="a8bb3-109">Resumen</span><span class="sxs-lookup"><span data-stu-id="a8bb3-109">Summary</span></span> |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType` | <span data-ttu-id="a8bb3-110">Coincide con todos los tipos denominados `MyType` y todos sus tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="a8bb3-110">Matches all types named `MyType` and all of their derived types.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType1|MyType2` | <span data-ttu-id="a8bb3-111">Coincide con todos los tipos denominados `MyType1` o `MyType2` y todos sus tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="a8bb3-111">Matches all types named either `MyType1` or `MyType2` and all of their derived types.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS.MyType` | <span data-ttu-id="a8bb3-112">Coincide con un tipo específico `MyType` con el nombre completo dado y todos sus tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="a8bb3-112">Matches specific type `MyType` with given fully qualified name and all of its derived types.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS1.MyType1|M:NS2.MyType2` | <span data-ttu-id="a8bb3-113">Coincide con tipos específicos `MyType1` y `MyType2` con los nombres completos respectivos, y todos sus tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="a8bb3-113">Matches specific types `MyType1` and `MyType2` with the respective fully qualified names, and all of their derived types.</span></span> |
