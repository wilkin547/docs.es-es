---
title: Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)
ms.date: 03/30/2017
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
ms.openlocfilehash: e74d34693446cca645003a9f93bc1777849e3182
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738410"
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a>Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)

Un archivo de directivas de tiempo de ejecución (.rd.xml) es un archivo de configuración XML que especifica si los elementos de programa designados están disponibles para reflexión. A continuación se muestra un ejemplo de un archivo de directivas de tiempo de ejecución:

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Namespace Name="Contoso.Cloud.AppServices" Serialize="Required Public" />
    <Namespace Name="ContosoClient.ViewModels" Serialize="Required Public" />
    <Namespace Name="ContosoClient.DataModel" Serialize="Required Public" />
    <Namespace Name="Contoso.Reader.UtilityLib" Serialize="Required Public" />

    <Namespace Name="System.Collections.ObjectModel" >
      <TypeInstantiation Name="ObservableCollection"
            Arguments="ContosoClient.DataModel.ProductItem" Serialize="Public" />
      <TypeInstantiation Name="ReadOnlyObservableCollection"
            Arguments="ContosoClient.DataModel.ProductGroup" Serialize="Public" />
    </Namespace>
  </Application>
</Directives>
```

## <a name="the-structure-of-a-runtime-directives-file"></a>Estructura de un archivo de directivas en tiempo de ejecución

El archivo de directivas de tiempo de ejecución utiliza el espacio de nombres `http://schemas.microsoft.com/netfx/2013/01/metadata`.

El elemento raíz es [Directives](directives-element-net-native.md). Puede contener cero o más elementos [Library](library-element-net-native.md) y cero o un elemento [Application](application-element-net-native.md), como se muestra en la estructura siguiente. Los atributos del elemento [Application](application-element-net-native.md) pueden definir directivas de reflexión en tiempo de ejecución para toda la aplicación, o puede actuar como contenedor de elementos secundarios. El elemento [Library](library-element-net-native.md), por otro lado, es simplemente un contenedor. Los elementos secundarios de los elementos [Application](application-element-net-native.md) y [Library](library-element-net-native.md) definen los tipos, métodos, campos, propiedades y eventos que están disponibles para reflexión.

Para obtener información de referencia, seleccione los elementos de la siguiente estructura o vea [Runtime Directive Elements](runtime-directive-elements.md) (Elementos de directivas en tiempo de ejecución) En la siguiente jerarquía, los puntos suspensivos marcan una estructura recursiva. La información entre paréntesis indica si el elemento es obligatorio u opcional y, si se utiliza, el número de instancias permitidas (una o varias).

- [Directives](directives-element-net-native.md) [1:1]
  - [Application](application-element-net-native.md) [0:1]
    - [Assembly](assembly-element-net-native.md) [0:M]
      - [Espacio de nombres](namespace-element-net-native.md) [0: M]. . .
      - [Tipo](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M]. . .
    - [Namespace](namespace-element-net-native.md) [0:M]
      - [Espacio de nombres](namespace-element-net-native.md) [0: M]. . .
      - [Tipo](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M]. . .
    - [Type](type-element-net-native.md) [0:M]
      - [Subtypes](subtypes-element-net-native.md) (subclases del tipo contenedor) [O:1]
      - [Tipo](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M]. . .
      - [AttributeImplies](attributeimplies-element-net-native.md) (el tipo contenedor es un atributo) [O:1]
      - [GenericParameter](genericparameter-element-net-native.md) [0:M]
      - [Method](method-element-net-native.md) [0:M]
        - [Parameter](parameter-element-net-native.md) [0:M]
        - [TypeParameter](typeparameter-element-net-native.md) [0:M]
        - [GenericParameter](genericparameter-element-net-native.md) [0:M]
      - [MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0:M]
      - [Property](property-element-net-native.md) [0:M]
      - [Field](field-element-net-native.md) [0:M]
      - [Event](event-element-net-native.md) [0:M]
    - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0:M]
      - [Tipo](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M]. . .
      - [Method](method-element-net-native.md) [0:M]
        - [Parameter](parameter-element-net-native.md) [0:M]
        - [TypeParameter](typeparameter-element-net-native.md) [0:M]
        - [GenericParameter](genericparameter-element-net-native.md) [0:M]
      - [MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0:M]
      - [Property](property-element-net-native.md) [0:M]
      - [Field](field-element-net-native.md) [0:M]
      - [Event](event-element-net-native.md) [0:M]
  - [Library](library-element-net-native.md) [0:M]
    - [Assembly](assembly-element-net-native.md) [0:M]
      - [Espacio de nombres](namespace-element-net-native.md) [0: M]. . .
      - [Tipo](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M]. . .
    - [Namespace](namespace-element-net-native.md) [0:M]
      - [Espacio de nombres](namespace-element-net-native.md) [0: M]. . .
      - [Tipo](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M]. . .
    - [Type](type-element-net-native.md) [0:M]
      - [Subtypes](subtypes-element-net-native.md) (subclases del tipo contenedor) [O:1]
      - [Tipo](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M]. . .
      - [AttributeImplies](attributeimplies-element-net-native.md) (el tipo contenedor es un atributo) [O:1]
      - [GenericParameter](genericparameter-element-net-native.md) [0:M]
      - [Method](method-element-net-native.md) [0:M]
      - [MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0:M]
      - [Property](property-element-net-native.md) [0:M]
      - [Field](field-element-net-native.md) [0:M]
      - [Event](event-element-net-native.md) [0:M]
    - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0:M]
      - [Tipo](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M]. . .
      - [Method](method-element-net-native.md) [0:M]
      - [MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0:M]
      - [Property](property-element-net-native.md) [0:M]
      - [Field](field-element-net-native.md) [0:M]
      - [Event](event-element-net-native.md) [0:M]

El elemento [Application](application-element-net-native.md) no puede tener atributos o puede tener los atributos de directiva tratados en la [sección sobre política y directivas de tiempo de ejecución](#Directives).

Un elemento [Library](library-element-net-native.md) tiene un solo atributo, `Name`, que especifica el nombre de una biblioteca o ensamblado sin la extensión de archivo. Por ejemplo, el siguiente elemento [Library](library-element-net-native.md) se aplica a un ensamblado denominado Extensions.dll.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <!-- Child elements go here -->
  </Application>
  <Library Name="Extensions">
     <!-- Child elements go here -->
  </Library>
</Directives>
```

<a name="Directives"></a>

## <a name="runtime-directives-and-policy"></a>Política y directivas de tiempo de ejecución

El elemento [Application](application-element-net-native.md) y los elementos secundarios de los elementos [Library](library-element-net-native.md) y [Application](application-element-net-native.md) expresan directiva; es decir, definen la forma en que una aplicación puede aplicar reflexión a un elemento de programa. El tipo de la directiva se define mediante un atributo del elemento (por ejemplo, `Serialize`). El valor de la directiva se define mediante el valor del atributo (por ejemplo, `Serialize="Required"`).

Cualquier directiva especificada por un atributo de un elemento se aplica a todos los elementos secundarios que no especifican ningún valor para esa directiva. Por ejemplo, si una directiva se especifica mediante un elemento [Type](type-element-net-native.md), esa directiva se aplica a todos los tipos y miembros contenidos para los que no se especifica explícitamente una directiva.

La directiva que puede expresarse mediante los elementos [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) y [Type](type-element-net-native.md) difiere de la que puede expresarse para miembros individuales (mediante los elementos [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md) y [Event](event-element-net-native.md)).

### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a>Especificar la directiva para ensamblados, espacios de nombres y tipos

Los elementos [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) y [Type](type-element-net-native.md) admiten los siguientes tipos de directivas:

- `Activate`. Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de las instancias.

- `Browse`. Controla la consulta de información sobre elementos del programa, pero no permite el acceso en tiempo de ejecución.

- `Dynamic`. Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.

- `Serialize`. Controla el acceso en tiempo de ejecución a constructores, campos y propiedades, para permitir que bibliotecas de terceros (como el serializador de JSON Newtonsoft) puedan serializar y deserializar las instancias de tipos.

- `DataContractSerializer`. Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.

- `DataContractJsonSerializer`. Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.

- `XmlSerializer`. Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.

- `MarshalObject`. Controla la directiva de cálculo de referencias de tipos de referencia para WinRT y COM.

- `MarshalDelegate`. Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.

- `MarshalStructure` . Controla la directiva para calcular referencias de estructuras a código nativo.

Los valores asociados con estos tipos de directiva son:

- `All`. Habilita la directiva para todos los tipos y miembros que no se eliminan con la cadena de herramientas.

- `Auto`. Usa el comportamiento predeterminado. (No especificar una directiva es equivalente a establecer esa directiva en `Auto`, a menos que se invalide la directiva, por ejemplo, por un elemento primario).

- `Excluded`. Deshabilita la directiva para el elemento de programa.

- `Public`. Habilita la directiva para tipos o miembros públicos a menos que la cadena de herramientas determine que el miembro es innecesario y, por tanto, lo quita. (En este último caso, debe utilizar `Required Public` para asegurarse de que el miembro se conserva y tiene capacidades de reflexión).

- `PublicAndInternal`. Habilita la directiva para tipos o miembros públicos e internos si la cadena de herramientas no los quita.

- `Required Public`. Exige que la cadena de herramientas mantenga los tipos y miembros públicos tanto si se utilizan como si no, y habilita la directiva para ellos.

- `Required PublicAndInternal`. Exige que la cadena de herramientas mantenga los tipos y miembros públicos e internos tanto si se utilizan como si no, y habilita la directiva para ellos.

- `Required All`. Exige que la cadena de herramientas mantenga todos los tipos y miembros tanto si se utilizan como si no, y habilita la directiva para ellos.

Por ejemplo, el siguiente archivo de directivas de tiempo de ejecución define una directiva para todos los tipos y miembros del ensamblado DataClasses.dll. Permite reflexión para la serialización de todas las propiedades públicas, permite buscar todos los tipos y miembros de tipo, permite la activación para todos los tipos (debido al atributo `Dynamic`) y permite la reflexión para todos los tipos y miembros públicos.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"
                Browse="All" Activate="PublicAndInternal"
                Dynamic="Public"  />
   </Application>
   <Library Name="UtilityLibrary">
     <!-- Child elements go here -->
   </Library>
</Directives>
```

### <a name="specifying-policy-for-members"></a>Especificar la directiva para los miembros

Los elementos [Property](property-element-net-native.md) y [Field](field-element-net-native.md) admiten los siguientes tipos de directivas:

- `Browse`: controla la consulta de información sobre este miembro, pero no permite el acceso en tiempo de ejecución.

- `Dynamic`: controla el acceso en tiempo de ejecución a todos los miembros de tipos, incluidos constructores, métodos, campos, propiedades y eventos, para permitir la programación dinámica. También controla la consulta de información sobre el tipo contenedor.

- `Serialize`: controla el acceso en tiempo de ejecución al miembro para permitir que las bibliotecas (como el serializador de JSON Newtonsoft) puedan serializar y deserializar las instancias de tipos. Esta directiva puede aplicarse a propiedades, campos y constructores.

Los elementos [Method](method-element-net-native.md) y [Event](event-element-net-native.md) admiten los siguientes tipos de directivas:

- `Browse`: controla la consulta de información sobre este miembro, pero no permite el acceso en tiempo de ejecución.

- `Dynamic`: controla el acceso en tiempo de ejecución a todos los miembros de tipos, incluidos constructores, métodos, campos, propiedades y eventos, para permitir la programación dinámica. También controla la consulta de información sobre el tipo contenedor.

 Los valores asociados con estos tipos de directiva son:

- `Auto`: usar el comportamiento predeterminado. (No especificar una política es equivalente a establecer esa directiva en `Auto`, a menos que algo la invalide).

- `Excluded`: no incluir nunca metadatos para el miembro.

- `Included`: habilitar la directiva, si el tipo primario está presente en la salida.

- `Required`: exige que la cadena de herramientas mantenga este miembro incluso si no parece usado, y habilitar una directiva para él.

## <a name="runtime-directives-file-semantics"></a>Semántica de archivos de directivas de tiempo de ejecución

La directiva puede definirse simultáneamente para elementos de nivel superior y de nivel inferior. Por ejemplo, puede definirse la directiva de un ensamblado y de algunos de los tipos contenidos en ese ensamblado. Si un elemento determinado de nivel inferior no está representado, hereda la directiva de su elemento primario. Por ejemplo, si un elemento `Assembly` está presente pero el elemento `Type` no, la directiva especificada en el elemento `Assembly` se aplica a cada tipo del ensamblado. Varios elementos también pueden aplicar una directiva al mismo elemento de programa. Por ejemplo, es posible que distintos elementos [Assembly](assembly-element-net-native.md) definan el mismo elemento de directiva para el mismo ensamblado de forma diferente. Las siguientes secciones explican cómo se resuelve la directiva para un tipo concreto en esos casos.

Un elemento [Type](type-element-net-native.md) o [Method](method-element-net-native.md) de un tipo o método genérico aplica su directiva a todas las creaciones de instancias que no tienen su propia directiva. Por ejemplo, un elemento `Type` que especifica la directiva de <xref:System.Collections.Generic.List%601> se aplica a todas las instancias construidas de ese tipo genérico, a menos que un elemento `List<Int32>` las invalide para un determinado tipo genérico construido (como un `TypeInstantiation`). De lo contrario, los elementos definen la directiva para el elemento de programa denominado.

Cuando un elemento es ambiguo, el motor busca coincidencias y, si encuentra a una coincidencia exacta, la utiliza. Si encuentra a varias coincidencias, habrá una advertencia o un error.

### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a>Si dos directivas directiva se aplican al mismo elemento de programa

Si dos elementos de diferentes archivos de directivas de tiempo de ejecución intentan establecer el mismo tipo de directiva para el mismo elemento de programa (por ejemplo, un ensamblado o tipo) en valores diferentes, el conflicto se resuelve como sigue:

1. Si el elemento `Excluded` está presente, tiene precedencia.

2. `Required` tiene precedencia sobre no `Required`.

3. `All` tiene precedencia sobre `PublicAndInternal`, que tiene precedencia sobre `Public`.

4. Cualquier valor explícito tiene precedencia sobre `Auto`.

Por ejemplo, si un único proyecto incluye los dos archivos de directivas de tiempo de ejecución siguientes, la directiva de serialización para DataClasses.dll se establece tanto en `Required Public` como en `All`. En este caso, la directiva de serialización se puede resolver como `Required All`.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"/>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="All" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

Sin embargo, si dos directivas de un único archivo de directivas de tiempo de ejecución intenta establecer el mismo tipo de directiva para el mismo elemento de programa, la herramienta de definición de esquema XML muestra un mensaje de error.

### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a>Si elementos primarios y secundarios aplican el mismo tipo de directiva

Los elementos secundarios invalidan a sus elementos primarios, incluido el valor `Excluded`. La invalidación es la razón principal por la que desearía especificar `Auto`.

En el siguiente ejemplo, el valor de directiva de serialización para todo lo contenido en `DataClasses` que no está en `DataClasses.ViewModels` sería `Required Public`, y todo lo que está tanto en `DataClasses` como en `DataClasses.ViewModels` sería `All`.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a>Si los genéricos abiertos y elementos con instancia aplican el mismo tipo de directiva

En el siguiente ejemplo, la directiva `Dictionary<int,int>` se asigna a `Browse` solo si el motor tiene otra razón para darle otorgarle la directiva `Browse` (que de lo contrario sería el comportamiento predeterminado); todos los miembros del resto de creaciones de instancias de <xref:System.Collections.Generic.Dictionary%602> se podrán examinar.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
      <Namespace Name="DataClasses.Generics" />
      <Type Name="Dictionary" Browse="All" />
      <TypeInstantiation Name="Dictionary"
                         Arguments="System.Int32,System.Int32" Browse="Auto" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="how-policy-is-inferred"></a>Cómo se infiere la directiva

Cada tipo de directiva tiene un conjunto diferente de reglas que determinan cómo la presencia de ese tipo de directiva afecta a otras construcciones.

#### <a name="the-effect-of-browse-policy"></a>El efecto de la directiva Browse

Aplicar la directiva `Browse` a un tipo implica los siguientes cambios de directiva:

- El tipo base del tipo que está marcado con directiva `Browse`.

- Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Browse`.

- Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.

- Cada interfaz del tipo que está marcado con la directiva `Browse`.

- El tipo de cada atributo que se aplica al tipo se marca con la directiva `Browse`.

- Si el tipo es genérico, cada tipo de restricción se marca con la directiva `Browse`.

- Si el tipo es genérico, los tipos sobre los cuales se crea una instancia del tipo se marcan con la directiva `Browse`.

Aplicar la directiva `Browse` a un método implica los siguientes cambios de directiva:

- Cada tipo de parámetro del método se marca con la directiva `Browse`.

- El tipo devuelto del método se marca con la directiva `Browse`.

- El tipo contenedor del método se marca con la directiva `Browse`.

- Si el método es método genérico para el que se creó una instancia, el método genérico sin instancia se marca con la directiva `Browse`.

- El tipo de cada atributo que se aplica al método se marca con la directiva `Browse`.

- Si el método es genérico, cada tipo de restricción se marca con la directiva `Browse`.

- Si el método es genérico, los tipos sobre los cuales se crea una instancia del método se marcan con la directiva `Browse`.

Aplicar la directiva `Browse` a un campo implica los siguientes cambios de directiva:

- El tipo de cada atributo que se aplica al campo se marca con la directiva `Browse`.

- El tipo del campo se marca con la directiva `Browse`.

- El tipo al que pertenece el campo se marca con la directiva `Browse`.

#### <a name="the-effect-of-dynamic-policy"></a>Efecto de la directiva Dynamic

Aplicar la directiva `Dynamic` a un tipo implica los siguientes cambios de directiva:

- El tipo base del tipo que está marcado con directiva `Dynamic`.

- Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Dynamic`.

- Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.

- Cada interfaz del tipo que está marcado con la directiva `Browse`.

- El tipo de cada atributo que se aplica al tipo se marca con la directiva `Browse`.

- Si el tipo es genérico, cada tipo de restricción se marca con la directiva `Browse`.

- Si el tipo es genérico, los tipos sobre los cuales se crea una instancia del tipo se marcan con la directiva `Browse`.

Aplicar la directiva `Dynamic` a un método implica los siguientes cambios de directiva:

- Cada tipo de parámetro del método se marca con la directiva `Browse`.

- El tipo devuelto del método se marca con la directiva `Dynamic`.

- El tipo contenedor del método se marca con la directiva `Dynamic`.

- Si el método es método genérico para el que se creó una instancia, el método genérico sin instancia se marca con la directiva `Browse`.

- El tipo de cada atributo que se aplica al método se marca con la directiva `Browse`.

- Si el método es genérico, cada tipo de restricción se marca con la directiva `Browse`.

- Si el método es genérico, los tipos sobre los cuales se crea una instancia del método se marcan con la directiva `Browse`.

- `MethodInfo.Invoke` puede invocar al método y la creación de delegados se hace posible mediante <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.

Aplicar la directiva `Dynamic` a un campo implica los siguientes cambios de directiva:

- El tipo de cada atributo que se aplica al campo se marca con la directiva `Browse`.

- El tipo del campo se marca con la directiva `Dynamic`.

- El tipo al que pertenece el campo se marca con la directiva `Dynamic`.

#### <a name="the-effect-of-activation-policy"></a>Efecto de la directiva Activation

Aplicar la directiva Activation a un tipo implica los siguientes cambios de directiva:

- Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Browse`.

- Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.

- Los constructores del tipo se marcan con la directiva `Activation`.

Aplicar la directiva `Activation` a un método implica el siguiente cambio de directiva:

- El constructor puede invocarse mediante los métodos <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> y <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>. En cuanto a los métodos, la directiva `Activation` solo afecta a constructores.

Aplicar la directiva `Activation` a un campo no tiene ningún efecto.

#### <a name="the-effect-of-serialize-policy"></a>Efecto de la directiva Serialize

La directiva `Serialize` permite el uso de serializadores comunes basados en la reflexión. Sin embargo, dado que Microsoft no conoce los patrones de acceso reflejo exacto de los serializadores que no son de Microsoft, esta directiva puede no ser totalmente efectiva.

Aplicar la directiva `Serialize` a un tipo implica los siguientes cambios de directiva:

- El tipo base del tipo que está marcado con directiva `Serialize`.

- Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Browse`.

- Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.

- Si el tipo es una enumeración, una matriz del tipo se marca con la directiva `Serialize`.

- Si el tipo implementa <xref:System.Collections.Generic.IEnumerable%601>, `T` se marca con la directiva `Serialize`.

- Si el tipo es <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601> o <xref:System.Collections.Generic.IReadOnlyList%601>, entonces `T[]` y <xref:System.Collections.Generic.List%601> se marcan con la directiva `Serialize`. Sin embargo, ningún miembro del tipo de interfaz se marca con la directiva `Serialize`.

- Si el tipo es <xref:System.Collections.Generic.List%601>, ningún miembro del tipo se marca con la directiva `Serialize`.

- Si el tipo es <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> se marca con la directiva `Serialize`. En cambio, ningún miembro del tipo se marca con la directiva `Serialize`.

- Si el tipo es <xref:System.Collections.Generic.Dictionary%602>, ningún miembro del tipo se marca con la directiva `Serialize`.

- Si el tipo implementa <xref:System.Collections.Generic.IDictionary%602>, `TKey` y `TValue` se marcan con la directiva `Serialize`.

- Todos los constructores, todos los descriptores de acceso de propiedad y todos los campos se marcan con la directiva `Serialize`.

Aplicar la directiva `Serialize` a un método implica los siguientes cambios de directiva:

- El tipo contenedor se marca con la directiva `Serialize`.

- El tipo devuelto del método se marca con la directiva `Serialize`.

Aplicar la directiva `Serialize` a un campo implica los siguientes cambios de directiva:

- El tipo contenedor se marca con la directiva `Serialize`.

- El tipo del campo se marca con la directiva `Serialize`.

#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserializer-policies"></a>Efecto de las directivas XmlSerializer, DataContractSerializer y DataContractJsonSerializer

A diferencia de la Directiva de `Serialize`, que está destinada a los serializadores basados en reflexión, las directivas <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> se utilizan para habilitar un conjunto de serializadores conocidos para la cadena de herramientas de .NET Native. Estos serializadores no se implementan mediante reflexión, pero el conjunto de tipos que se pueden serializar en tiempo de ejecución se determina de manera similar a los tipos que admiten reflexión.

Aplicar una de estas directivas a un tipo permite la serialización del tipo con el serializador correspondiente. Además, los tipos que el motor de serialización puede determinar de forma estática que necesitan serialización también se podrán serializar.

Estas directivas no tienen efecto sobre los campos o métodos.

Para más información, vea la sección "Diferencias en los serializadores" en [Migrar la aplicación de la Tienda Windows a .NET Native](migrating-your-windows-store-app-to-net-native.md).

## <a name="see-also"></a>Consulte también

- [Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)](runtime-directive-elements.md)
- [Reflexión y .NET Native](reflection-and-net-native.md)
