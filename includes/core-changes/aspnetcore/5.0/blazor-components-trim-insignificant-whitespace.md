---
ms.openlocfilehash: ca369c4e3f78648c6e8e0bcb5d54711d3009a769
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174273"
---
### <a name="blazor-insignificant-whitespace-trimmed-from-components-at-compile-time"></a>Blazor: Espacio en blanco no significativo recortado de componentes en el tiempo de compilación

A partir de ASP.NET Core 5.0, versión preliminar 7, el compilador de Razor omite el espacio en blanco no significativo de los componentes de Blazor (archivos de *.razor*) en el tiempo de compilación. Para obtener información, consulte el tema [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568).

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 7)

#### <a name="old-behavior"></a>Comportamiento anterior

En las versiones 3.x de Blazor Server y Blazor WebAssembly, se respeta el espacio en blanco en el código fuente de un componente. Los nodos de texto de espacio en blanco solo se representan en el Document Object Model (DOM) del explorador aunque no haya ningún efecto visual.

Considere el siguiente código de componente Blazor:

```razor
<ul>
    @foreach (var item in Items)
    {
        <li>
            @item.Text
        </li>
    }
</ul>
```

En el ejemplo anterior se representan dos nodos de espacios en blanco:

* Fuera del bloque de código `@foreach`.
* Alrededor del elemento `<li>`.
* Alrededor de la salida de `@item.Text`.

Una lista que contiene 100 elementos da como resultado 402 nodos de espacios en blanco. Esta cantidad es más de la mitad de todos los nodos representados, aunque ninguno de los nodos de espacios en blanco afecte visualmente a la salida representada.

Al representar HTML estático para componentes, no se conservaba el espacio en blanco dentro de una etiqueta. Por ejemplo, vea el origen del siguiente componente:

```razor
<foo        bar="baz"     />
```

No se conserva el espacio en blanco. La salida representada previamente es:

```razor
<foo bar="baz" />
```

#### <a name="new-behavior"></a>Comportamiento nuevo

A menos que se use la Directiva de `@preservewhitespace` con `true` de valor, se quitan los nodos de espacios en blanco si:

* Están delante o detrás de un elemento.
* Están delante o detrás de un parámetro `RenderFragment`. Por ejemplo, el contenido secundario se pasa a otro componente.
* Precede o sigue a un bloque de código de C#, como `@if` y `@foreach`.

#### <a name="reason-for-change"></a>Motivo del cambio

Un objetivo para Blazor en ASP.NET Core 5,0 es mejorar el rendimiento de la representación y la diferenciación. Los nodos de árbol de espacios en blanco no significativos consumieron hasta un 40 % del tiempo de representación en las pruebas comparativas.

#### <a name="recommended-action"></a>Acción recomendada

En la mayoría de los casos, el diseño visual del componente representado no se ve afectado. Sin embargo, la eliminación de espacios en blanco puede afectar a la salida representada cuando se usa una regla de CSS como `white-space: pre`. Para deshabilitar esta optimización de rendimiento y conservar el espacio en blanco, realice una de las siguientes acciones:

* Agregue la directiva `@preservewhitespace true` en la parte superior del archivo *.razor* para aplicar las preferencias a un componente específico.
* Agregue la directiva `@preservewhitespace true` dentro de un archivo *_Imports.razor* para aplicar la preferencia a un subdirectorio completo o a todo el proyecto.

En la mayoría de los casos, no se requiere ninguna acción, ya que las aplicaciones normalmente seguirán funcionando con normalidad (pero más rápido). Si la eliminación de espacios en blanco provoca problemas en un componente determinado, use `@preservewhitespace true` de ese componente para deshabilitar esta optimización.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!--

#### Affected APIs

Not detectable via API analysis

-->
