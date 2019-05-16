---
title: Atributos
description: Obtenga información sobre cómo F# atributos permiten que los metadatos que se aplicará a una construcción de programación.
ms.date: 05/16/2016
ms.openlocfilehash: fed4c549b95d6d3701ab81cf5d62add411c16038
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642024"
---
# <a name="attributes"></a>Atributos

Atributos permiten que los metadatos que se aplicará a una construcción de programación.

## <a name="syntax"></a>Sintaxis

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, el *destino* es opcional y, si está presente, especifica el tipo de entidad de programa que se aplica el atributo. Los valores válidos para *destino* se muestran en la tabla que aparece más adelante en este documento.

El *nombre del atributo* hace referencia al nombre (posiblemente calificado con espacios de nombres) de un tipo de atributo válido, con o sin el sufijo `Attribute` que normalmente se usa en nombres de tipo de atributo. Por ejemplo, el tipo `ObsoleteAttribute` puede abreviar a `Obsolete` en este contexto.

El *argumentos* son los argumentos al constructor del tipo de atributo. Si un atributo tiene un constructor predeterminado, se pueden omitir la lista de argumentos y los paréntesis. Los atributos admiten argumentos posicionales y argumentos con nombre. *Los argumentos posicionales* son argumentos que se usan en el orden en que aparecen. Pueden utilizar argumentos con nombre si el atributo tiene propiedades públicas. Puede establecer estas opciones mediante la sintaxis siguiente en la lista de argumentos.

```
*property-name* = *property-value*
```

Inicializaciones de propiedad pueden estar en cualquier orden, pero deben seguir los argumentos posicionales. La siguiente es un ejemplo de un atributo que usa argumentos posicionales e inicializaciones de propiedad.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

En este ejemplo, el atributo es `DllImportAttribute`, aquí se usa en forma abreviada. El primer argumento es un parámetro de posición y el segundo es una propiedad.

Los atributos son una construcción de programación de .NET que permite a un objeto que se conoce como un *atributo* va a asociar a un tipo u otro elemento de programa. El elemento de programa al que se aplica un atributo se conoce como el *destino del atributo*. Normalmente, el atributo contiene metadatos acerca de su destino. En este contexto, los metadatos podrían ser ningún dato sobre el tipo que no sean sus campos y los miembros.

Los atributos F# se pueden aplicar a las construcciones de programación siguientes: funciones, métodos, ensamblados, módulos, tipos (clases, registros, estructuras, interfaces, delegados, enumeraciones, uniones etc.), constructores, propiedades, campos, los parámetros, escriba los parámetros y valores devueltos. No se admiten atributos en `let` enlaces dentro de clases, las expresiones o expresiones de flujo de trabajo.

Normalmente, la declaración de atributos aparece directamente antes de la declaración del destino del atributo. Juntos, como se indica a continuación, se pueden usar varias declaraciones de atributo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

Puede consultar los atributos en tiempo de ejecución mediante la reflexión. NET.

Puede declarar varios atributos individualmente, como se muestra en el ejemplo de código anterior, o bien puede declarar en un conjunto de corchetes si usa un punto y coma para separar los atributos individuales y los constructores, como se muestra aquí.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

Atributos encontrados normalmente incluyen la `Obsolete` atributo, los atributos de las consideraciones de seguridad, los atributos para la compatibilidad con COM, atributos relacionados con la propiedad del código y los atributos que indica si se puede serializar un tipo. En el ejemplo siguiente se muestra el uso de la `Obsolete` atributo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

Para los destinos de atributo `assembly` y `module`, aplicar los atributos a un nivel superior `do` enlace en el ensamblado. Puede incluir la palabra `assembly` o `module` en la declaración de atributo, como se indica a continuación.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

Si se omite el destino del atributo para un atributo aplicado a un `do` enlace, el F# compilador intenta determinar el destino del atributo que tenga sentido para ese atributo. Muchas clases de atributos tienen un atributo de tipo `System.AttributeUsageAttribute` que incluye información sobre los posibles destinos admitidos para ese atributo. Si el `System.AttributeUsageAttribute` indica que el atributo admite funciones como destinos, se obtendrá el atributo que se aplicará al punto de entrada principal del programa. Si el `System.AttributeUsageAttribute` indica que el atributo admite ensamblados como destinos, el compilador usa el atributo se aplique al ensamblado. La mayoría de los atributos no se aplican a las funciones y ensamblados, pero en los casos donde lo hacen, se toma el atributo que se aplicará a la función principal del programa. Si el destino del atributo se especifica explícitamente, el atributo se aplica al destino especificado.

Aunque normalmente no es necesario especificar el atributo de destino explícitamente, los valores válidos para *destino* en un atributo que se muestran en la siguiente tabla, junto con ejemplos de uso.

<table>
  <tr>
    <th>Destino de atributo</td>
    <th>Ejemplo</td> 
  </tr>
  <tr>
    <td>ensamblado</td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]<code></pre></td> 
  </tr>
  <tr>
    <td>return</td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1<code></pre></td> 
  </tr>
  <tr>
    <td>campo</td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int<code></pre></td> 
  </tr>
  <tr>
    <td>propiedad</td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x<code></pre></td> 
  </tr>
  <tr>
    <td>param</td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10<code></pre></td> 
  </tr>
  <tr>
    <td>type</td>
    <td>
        <pre lang="fsharp"><code>
        [&lt;type: StructLayout(Sequential)&gt;] 
        type MyStruct = 
        struct 
        x : byte
        y : int
        end
        <code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
