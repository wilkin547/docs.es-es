---
ms.openlocfilehash: 83644b9205d650da68c910095dd1d22a14940c44
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "97366826"
---
### <a name="exclude-specific-symbols"></a><span data-ttu-id="a209b-101">Excluir símbolos específicos</span><span class="sxs-lookup"><span data-stu-id="a209b-101">Exclude specific symbols</span></span>

<span data-ttu-id="a209b-102">Puede excluir símbolos específicos, como tipos y métodos, del análisis.</span><span class="sxs-lookup"><span data-stu-id="a209b-102">You can exclude specific symbols, such as types and methods, from analysis.</span></span> <span data-ttu-id="a209b-103">Por ejemplo, para especificar que la regla no se debe ejecutar en ningún código dentro de los tipos denominados `MyType` , agregue el siguiente par clave-valor a un archivo *. editorconfig* en el proyecto:</span><span class="sxs-lookup"><span data-stu-id="a209b-103">For example, to specify that the rule should not run on any code within types named `MyType`, add the following key-value pair to an *.editorconfig* file in your project:</span></span>

```ini
dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType
```

<span data-ttu-id="a209b-104">Formatos de nombre de símbolo permitidos en el valor de opción (separados por `|` ):</span><span class="sxs-lookup"><span data-stu-id="a209b-104">Allowed symbol name formats in the option value (separated by `|`):</span></span>

- <span data-ttu-id="a209b-105">Solo nombre de símbolo (incluye todos los símbolos con el nombre, sin tener en cuenta el tipo o espacio de nombres contenedor).</span><span class="sxs-lookup"><span data-stu-id="a209b-105">Symbol name only (includes all symbols with the name, regardless of the containing type or namespace).</span></span>
- <span data-ttu-id="a209b-106">Nombres completos en el [formato de ID](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings). de documentación del símbolo.</span><span class="sxs-lookup"><span data-stu-id="a209b-106">Fully qualified names in the symbol's [documentation ID format](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings).</span></span> <span data-ttu-id="a209b-107">Cada nombre de símbolo requiere un prefijo de tipo símbolo, como `M:` para los métodos, `T:` para los tipos y `N:` para los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="a209b-107">Each symbol name requires a symbol-kind prefix, such as `M:` for methods, `T:` for types, and `N:` for namespaces.</span></span>
- <span data-ttu-id="a209b-108">`.ctor` para constructores y `.cctor` para constructores estáticos.</span><span class="sxs-lookup"><span data-stu-id="a209b-108">`.ctor` for constructors and `.cctor` for static constructors.</span></span>

<span data-ttu-id="a209b-109">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a209b-109">Examples:</span></span>

| <span data-ttu-id="a209b-110">Valor de la opción</span><span class="sxs-lookup"><span data-stu-id="a209b-110">Option Value</span></span> | <span data-ttu-id="a209b-111">Resumen</span><span class="sxs-lookup"><span data-stu-id="a209b-111">Summary</span></span> |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType` | <span data-ttu-id="a209b-112">Coincide con todos los símbolos denominados `MyType` .</span><span class="sxs-lookup"><span data-stu-id="a209b-112">Matches all symbols named `MyType`.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType1|MyType2` | <span data-ttu-id="a209b-113">Coincide con todos los símbolos denominados `MyType1` o `MyType2` .</span><span class="sxs-lookup"><span data-stu-id="a209b-113">Matches all symbols named either `MyType1` or `MyType2`.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS.MyType.MyMethod(ParamType)` | <span data-ttu-id="a209b-114">Coincide `MyMethod` con un método específico con la firma completa especificada.</span><span class="sxs-lookup"><span data-stu-id="a209b-114">Matches specific method `MyMethod` with the specified fully qualified signature.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS1.MyType1.MyMethod1(ParamType)|M:NS2.MyType2.MyMethod2(ParamType)` | <span data-ttu-id="a209b-115">Coincide con métodos específicos `MyMethod1` y `MyMethod2` con las firmas completas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="a209b-115">Matches specific methods `MyMethod1` and `MyMethod2` with the respective fully qualified signatures.</span></span> |
