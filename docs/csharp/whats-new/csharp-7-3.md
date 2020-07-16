---
title: Novedades de C# 7.3
description: Información general sobre las nuevas características en C# 7.3
ms.date: 05/16/2018
ms.openlocfilehash: cd8f554516fb5078d9d2ed1eec787f36e8f4c7a7
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174762"
---
# <a name="whats-new-in-c-73"></a>Novedades de C# 7.3

Hay dos temas principales para la versión C# 7.3. Un tema proporciona características que permiten al código seguro ser tan eficaz como el código no seguro. El segundo tema proporciona mejoras incrementales en las características existentes. Además, se han agregado nuevas opciones de compilador en esta versión.

Las siguientes características nuevas admiten el tema del mejor rendimiento para código seguro:

- Puede tener acceso a campos fijos sin anclar.
- Puede volver a asignar variables locales `ref`.
- Puede usar inicializadores en matrices `stackalloc`.
- Puede usar instrucciones `fixed` con cualquier tipo que admita un patrón.
- Puede usar restricciones genéricas adicionales.

Se hicieron las mejoras siguientes a las características existentes:

- Puede probar `==` y `!=` con los tipos de tupla.
- Puede usar variables de expresión en más ubicaciones.
- Puede asociar atributos al campo de respaldo de las propiedades autoimplementadas.
- Se ha mejorado la resolución de métodos cuando los argumentos difieren por `in`.
- Ahora, la resolución de sobrecarga tiene menos casos ambiguos.

Las nuevas opciones del compilador son:

- `-publicsign` para habilitar la firma de ensamblados de software de código abierto (OSS).
- `-pathmap` para proporcionar una asignación para los directorios de origen.

El resto de este artículo proporciona información detallada y vínculos para obtener más información sobre cada una de las mejoras. Puede explorar estas características en su entorno mediante la herramienta global `dotnet try`:

1. Instale la herramienta global [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).
1. Clone el repositorio [dotnet/try-samples](https://github.com/dotnet/try-samples).
1. Establezca el directorio actual en el subdirectorio *csharp7* para el repositorio *try-samples*.
1. Ejecute `dotnet try`.

## <a name="enabling-more-efficient-safe-code"></a>Habilitación de código seguro más eficaz

Debería poder escribir código de C# de forma segura que tenga el mismo rendimiento que el código no seguro. El código seguro evita clases de errores, como desbordamientos de búfer, punteros perdidos y otros errores de acceso a la memoria. Estas nuevas características amplían las capacidades de código seguro comprobable. Procure escribir más código utilizando construcciones seguras. Estas características lo facilitan en gran medida.

### <a name="indexing-fixed-fields-does-not-require-pinning"></a>Indexación de campos `fixed` sin requerir anclaje

Considere esta estructura:

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

En versiones anteriores de C#, era necesario anclar una variable para acceder a uno de los enteros que forman parte de `myFixedField`. Ahora, el código siguiente se compila sin anclar la variable `p` dentro de una instrucción `fixed` independiente:

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

La variable `p` tiene acceso a un elemento en `myFixedField`. No es necesario declarar otra variable `int*` independiente. Tenga en cuenta que todavía necesita un contexto `unsafe`. En versiones anteriores de C#, es necesario declarar un segundo puntero fijo:

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

Para más información, consulte el artículo sobre la [instrucción `fixed`](../language-reference/keywords/fixed-statement.md).

### <a name="ref-local-variables-may-be-reassigned"></a>Las variables locales de `ref` se pueden reasignar

Ahora, las variables locales de `ref` pueden reasignarse para hacer referencia a instancias diferentes después de haberse inicializado. El código siguiente ahora compila:

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

Para obtener más información, vea el artículo sobre valores devueltos de [`ref` y `ref`locales](../programming-guide/classes-and-structs/ref-returns.md), así como el artículo sobre [`foreach`](../language-reference/keywords/foreach-in.md).

### <a name="stackalloc-arrays-support-initializers"></a>Las matrices `stackalloc` admiten inicializadores

Ha podido especificar los valores para los elementos en una matriz cuando la inicializa:

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

Ahora, esa misma sintaxis se puede aplicar a las matrices que se declaran con `stackalloc`:

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

Para obtener más información, vea el artículo [Operador `stackalloc`](../language-reference/operators/stackalloc.md).

### <a name="more-types-support-the-fixed-statement"></a>Hay más tipos compatibles con la instrucción `fixed`

La instrucción `fixed` admite un conjunto limitado de tipos. A partir de C# 7.3, cualquier tipo que contenga un método `GetPinnableReference()` que devuelve un `ref T` o `ref readonly T` puede ser `fixed`. La adición de esta característica significa que `fixed` puede utilizarse con <xref:System.Span%601?displayProperty=nameWithType> y tipos relacionados.

Para más información, vea el artículo sobre la [instrucción `fixed`](../language-reference/keywords/fixed-statement.md) en la referencia del lenguaje.

### <a name="enhanced-generic-constraints"></a>Restricciones genéricas mejoradas

Ahora puede especificar el tipo <xref:System.Enum?displayProperty=nameWithType> o <xref:System.Delegate?displayProperty=nameWithType> como restricciones de clase base para un parámetro de tipo.

También puede usar la nueva restricción `unmanaged` para especificar que el parámetro de tipo debe ser un [tipo no administrado](../language-reference/builtin-types/unmanaged-types.md) que no acepta valores NULL.

Para obtener más información, vea los artículos sobre [restricciones genéricas de `where`](../language-reference/keywords/where-generic-type-constraint.md) y [restricciones sobre parámetros de tipo](../programming-guide/generics/constraints-on-type-parameters.md).

Agregar estas restricciones a tipos existentes es un [cambio incompatible](version-update-considerations.md#incompatible-changes). Los tipos genéricos cerrados puede que ya no cumplan estas nuevas restricciones.

## <a name="make-existing-features-better"></a>Mejora de las características existentes

El segundo tema proporciona las mejoras a las características del lenguaje. Estas características mejoran la productividad al escribir C#.

### <a name="tuples-support--and-"></a>Compatibilidad con tuplas `==` y `!=`

Los tipos de tupla de C# ahora admiten `==` y `!=`. Si desea más información, consulte la sección [Igualdad de tupla](../language-reference/builtin-types/value-tuples.md#tuple-equality) del artículo [Tipos de tupla](../language-reference/builtin-types/value-tuples.md).

### <a name="attach-attributes-to-the-backing-fields-for-auto-implemented-properties"></a>Asociación de atributos a los campos de respaldo para las propiedades autoimplementadas

Esta sintaxis ahora se admite:

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

El atributo `SomeThingAboutFieldAttribute` se aplica al campo de respaldo generado por el compilador para `SomeProperty`. Para obtener más información, vea [atributos](../programming-guide/concepts/attributes/index.md) en la guía de programación de C#.

### <a name="in-method-overload-resolution-tiebreaker"></a>Factor de desempate de resolución de sobrecargas del método `in`

Cuando se agregó el modificador de argumentos `in`, estos dos métodos causarían una ambigüedad:

```csharp
static void M(S arg);
static void M(in S arg);
```

Ahora, la sobrecarga por valor (primera en el ejemplo anterior) es mejor que la de la versión de referencia de solo lectura. Para llamar a la versión con el argumento de referencia de solo lectura, debe incluir el modificador `in` cuando llame al método.

> [!NOTE]
> Esto se implementó como una corrección de errores. Ya no es ambiguo, incluso con la versión de lenguaje establecida en "7.2".

Para obtener más información, consulte el artículo sobre el [modificador de parámetros`in`](../language-reference/keywords/in-parameter-modifier.md).

### <a name="extend-expression-variables-in-initializers"></a>Ampliación de variables de la expresión en inicializadores

La sintaxis que se agregó en C# 7.0 para permitir declaraciones de variable `out` se ha ampliado para incluir inicializadores de campo, inicializadores de propiedad, inicializadores de constructor y cláusulas de consulta. Permite código como el siguiente ejemplo:

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : base(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

### <a name="improved-overload-candidates"></a>Mejoras en los candidatos de sobrecarga

En cada versión, las reglas de resolución de sobrecarga se actualizan para abordar situaciones en las que las invocaciones de métodos ambiguos tienen una opción "obvia". Esta versión agrega tres nuevas reglas para ayudar a que el compilador elija la opción obvia:

1. Cuando un grupo de métodos contiene tanto miembros de instancia como estáticos, el compilador descarta los miembros de la instancia si el método fue invocado sin un receptor o contexto de instancia. El compilador descarta los miembros estáticos si el método se invocó con un receptor de instancia. Cuando no hay ningún receptor, el compilador incluye solo miembros estáticos en un contexto estático; de lo contrario, miembros estáticos y de instancia. Cuando el receptor es ambiguamente una instancia o un tipo, el compilador incluye ambos. Un contexto estático, donde no se puede usar un receptor de instancia `this` implícito, incluye el cuerpo de miembros donde no se define `this`, como miembros estáticos, así como lugares donde `this` no se puede usar, como inicializadores de campo e inicializadores-constructores.
1. Cuando un grupo de métodos contiene algunos métodos genéricos cuyos argumentos de tipo no cumplen con sus restricciones, estos miembros se eliminan del conjunto de candidatos.
1. En el caso de una conversión de grupo de métodos, los métodos candidatos cuyo tipo de valor devuelto no coincide con el tipo de valor devuelto del delegado se eliminan del conjunto.

Solo notará este cambio porque encontrará menos errores de compilación para sobrecargas ambiguas de métodos cuando esté seguro de qué método es mejor.

## <a name="new-compiler-options"></a>Nuevas opciones del compilador

Las nuevas opciones del compilador admiten nuevos escenarios de DevOps y compilación de programas de C#.

### <a name="public-or-open-source-signing"></a>Firma pública o de código abierto

La opción del compilador `-publicsign` indica al compilador que firme el ensamblado con una clave pública. El ensamblado se marca como firmado, pero la firma se toma de la clave pública. Esta opción le permite crear ensamblados firmados a partir de proyectos de código abierto utilizando una clave pública.

Para obtener más información, vea el artículo [-filealign (Opciones del compilador de C#)](../language-reference/compiler-options/publicsign-compiler-option.md).

### <a name="pathmap"></a>pathmap

La opción del compilador `-pathmap` indica al compilador que reemplace las rutas de acceso de origen del entorno de compilación por rutas de acceso de origen asignadas. La opción `-pathmap` controla la ruta de acceso de origen escrita por el compilador en los archivos PDB o para <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.

Para obtener más información, vea el artículo [-pathmap (opciones del compilador de C#)](../language-reference/compiler-options/pathmap-compiler-option.md).
