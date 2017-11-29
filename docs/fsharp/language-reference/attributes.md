---
title: Atributos (F#)
description: "Obtenga información acerca de cómo F # atributos permiten que los metadatos que se aplicará a una construcción de programación."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 95c001e6-3708-4d04-a850-d855f78eb51e
ms.openlocfilehash: 88098e51d19a86f501c35abe3408524378f147b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="attributes"></a>Atributos

Atributos permiten que los metadatos que se aplicará a una construcción de programación.

## <a name="syntax"></a>Sintaxis

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, el *destino* es opcional y, si está presente, especifica el tipo de entidad de programa que se aplica el atributo. Los valores válidos para *destino* se muestran en la tabla que aparece más adelante en este documento.

El *nombre del atributo* hace referencia al nombre (posiblemente calificado con espacios de nombres) de un tipo de atributo válido, con o sin el sufijo `Attribute` que normalmente se usa en nombres de tipo de atributo. Por ejemplo, el tipo `ObsoleteAttribute` se puede abreviar simplemente `Obsolete` en este contexto.

El *argumentos* son los argumentos para el constructor para el tipo de atributo. Si un atributo tiene un constructor predeterminado, se pueden omitir la lista de argumentos y los paréntesis. Los atributos admiten argumentos posicionales y argumentos con nombre. *Argumentos posicionales* son los argumentos que se utilizan en el orden en que aparecen. Argumentos con nombre se pueden utilizar si el atributo tiene propiedades públicas. Puede establecer estas opciones mediante la sintaxis siguiente en la lista de argumentos.

```
*property-name* = *property-value*
```

Dichas inicializaciones de propiedad pueden estar en cualquier orden, pero debe seguir los argumentos posicionales. Aquí te mostramos un ejemplo de un atributo que utiliza argumentos posicionales e inicializaciones de propiedad.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

En este ejemplo, el atributo es `DllImportAttribute`, aquí se utiliza en forma abreviada. El primer argumento es un parámetro posicional y el segundo es una propiedad.

Los atributos son una construcción de programación de .NET que permite a un objeto que se conoce como un *atributo* asociarse con un tipo u otro elemento de programa. El elemento de programa al que se aplica un atributo se conoce como el *destino del atributo*. El atributo suele contener metadatos acerca de su destino. En este contexto, los metadatos podrían ser cualquier dato sobre el tipo, excepto sus campos y miembros.

Atributos en F # se pueden aplicar a las construcciones de programación siguientes: funciones, métodos, ensamblados, módulos, tipos (clases, registros, estructuras, interfaces, delegados, enumeraciones, uniones etc.), constructores, propiedades, campos, parámetros, parámetros de tipo y valores devueltos. No se permiten atributos en `let` enlaces dentro de las clases, las expresiones o expresiones de flujo de trabajo.

Normalmente, la declaración de atributos aparece directamente antes de la declaración del destino del atributo. Varias declaraciones de atributo se pueden utilizar juntos, como se indica a continuación.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

Puede consultar los atributos en tiempo de ejecución utilizando la reflexión. NET.

Puede declarar varios atributos individualmente, como se muestra en el ejemplo de código anterior, o bien puede declarar en un conjunto de corchetes si utiliza un punto y coma para separar los atributos individuales y los constructores, como se muestra aquí.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

Atributos encontrados normalmente incluyen el `Obsolete` atributos de atributo, atributos de consideraciones de seguridad, compatibilidad con COM, atributos relacionados con las que la propiedad del código y atributos que indica si se puede serializar un tipo. En el ejemplo siguiente se muestra el uso de la `Obsolete` atributo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

Para los destinos de atributo `assembly` y `module`, aplicar los atributos a un nivel superior `do` enlace en el ensamblado. Puede incluir la palabra `assembly` o `module` en la declaración de atributo, como se indica a continuación.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

Si se omite el destino del atributo para un atributo aplicado a un `do` de enlace, el compilador de F # intenta determinar el destino del atributo que tenga sentido para ese atributo. Muchas clases de atributos tienen un atributo de tipo `System.AttributeUsageAttribute` que incluye información sobre los posibles destinos admitidos para ese atributo. Si el `System.AttributeUsageAttribute` indica que el atributo admite funciones como destinos, el atributo se lleva a cabo para aplicar al punto de entrada principal del programa. Si el `System.AttributeUsageAttribute` indica que el atributo admite ensamblados como destinos, el compilador usa el atributo para aplicar al ensamblado. Mayoría de los atributos no se aplica a las funciones y ensamblados, pero en casos donde lo hacen, se realiza el atributo al que se aplica a la función principal del programa. Si el destino del atributo se especifica explícitamente, el atributo se aplica al destino especificado.

Aunque normalmente no es necesario especificar el atributo de destino explícitamente, los valores válidos para *destino* en un atributo se muestran en la siguiente tabla, junto con ejemplos de uso.

<table>
  <tr>
    <th>Destino del atributo</td>
    <th>Ejemplo</td> 
  </tr>
  <tr>
    <td>ensamblado</td>
    <td>`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</td> 
  </tr>
  <tr>
    <td>return</td>
    <td>' permiten function1 x: [<return: Obsolete>] int = x + 1'</td> 
  </tr>
  <tr>
    <td>campo</td>
    <td>' [<field: DefaultValue>] x: int mutable val'</td> 
  </tr>
  <tr>
    <td>propiedad</td>
    <td>' [<property: Obsolete>] esto. MyProperty = x'</td> 
  </tr>
  <tr>
    <td>Param</td>
    <td>' miembro de este. MyMethod ([<param: Out>] x: ref<int>) = x: = 10'</td> 
  </tr>
  <tr>
    <td>type</td>
    <td>
        ```
        [<type: StructLayout(Sequential)>] Escriba MyStruct = struct x: byte y: int final```
    </td> 
  </tr>
</table>

## <a name="see-also"></a>Vea también

[Referencia del lenguaje F#](index.md)
