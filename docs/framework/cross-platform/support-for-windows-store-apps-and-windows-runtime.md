---
description: 'Más información: Compatibilidad de .NET Framework con aplicaciones de Microsoft Store y Windows Runtime'
title: Compatibilidad de .NET Framework con aplicaciones de Microsoft Store y Windows Runtime
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Store apps, .NET Framework support for
- Windows Runtime, .NET Framework support for
- .NET for Windows Store apps
- .NET Framework, and Windows Store apps
- .NET Framework, and Windows Runtime
ms.assetid: 6fa7d044-ae12-4c54-b8ee-50915607a565
ms.openlocfilehash: 851deb30420eb19c4fe2037bebe2cf8f84743c49
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "102402265"
---
# <a name="net-framework-support-for-microsoft-store-apps-and-windows-runtime"></a>Compatibilidad de .NET Framework con aplicaciones de Microsoft Store y Windows Runtime

.NET Framework 4.5 admite varios escenarios de desarrollo de software con Windows Runtime. Estos escenarios se clasifican en tres categorías:

- Desarrollo de aplicaciones de la Tienda Windows 8.x con controles de XAML, como se describe en la [Guía básica para aplicaciones de la Tienda Windows con C# o Visual Basic](/previous-versions/windows/apps/br229583(v=win.10)), los [Procedimientos (XAML)](/previous-versions/windows/apps/br229566(v=win.10)) y la [Información general sobre .NET para aplicaciones de la Tienda Windows](/previous-versions/windows/apps/br230302(v=vs.140)).

- Desarrollo de bibliotecas de clases para utilizarlas en las aplicaciones de la Tienda Windows 8.x creadas con .NET Framework.

- Desarrollo de componentes de Windows Runtime, empaquetados en archivos .WinMD, que se pueden usar en cualquier lenguaje de programación compatible con Windows Runtime. Por ejemplo, vea [Creación de componentes de Windows Runtime en C# y Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

En este artículo se describe la compatibilidad que proporciona .NET Framework con las tres categorías y se describen los escenarios para los componentes de Windows Runtime. En la primera sección se incluye información básica sobre la relación entre .NET Framework y Windows Runtime, y se explican algunas singularidades que se pueden encontrar en el sistema de ayuda y el IDE. En la [segunda sección](#WindowsRuntimeComponents) se describen los escenarios para desarrollar los componentes de Windows Runtime.

## <a name="the-basics"></a>Conceptos básicos

.NET Framework admite los tres escenarios de desarrollo enumerados anteriormente proporcionando .NET para aplicaciones de la Tienda Windows 8.x y admitiendo Windows Runtime.

- Los [espacios de nombres de .NET Framework y Windows Runtime](/previous-versions/windows/apps/br230302(v=vs.140)#net-framework-and-windows-runtime-namespaces) proporcionan una vista simplificada de las bibliotecas de clases de .NET Framework e incluyen solo los tipos y miembros que se pueden usar para crear aplicaciones de la Tienda Windows 8.x y componentes de Windows Runtime.

  - Cuando se usa Visual Studio (Visual Studio 2012 o posterior) para desarrollar una aplicación de la Tienda Windows 8.x o un componente de Windows Runtime, un conjunto de ensamblados de referencia garantiza que solo se vean los tipos y miembros pertinentes.

  - Este conjunto racionalizado de API optimizado se simplifica aún más mediante la eliminación de las características duplicadas en .NET Framework o que duplican características de Windows Runtime. Por ejemplo, solo contiene las versiones genéricas de los tipos de colección, y se ha eliminado el modelo de objetos de documento XML a favor del conjunto de API de XML de Windows Runtime.

  - También se han eliminado las características que simplemente encapsulan la API del sistema operativo, porque resulta sencillo llamar a Windows Runtime desde el código administrado.

  Para más información sobre .NET para aplicaciones de la Tienda Windows 8.x, vea la [Información general sobre .NET para aplicaciones de la Tienda Windows](/previous-versions/windows/apps/br230302(v=vs.140)). Para más información sobre el proceso de selección de la API, vea la entrada sobre [.NET para aplicaciones estilo Metro](https://devblogs.microsoft.com/dotnet/net-for-metro-style-apps/) en el blog de .NET.

- [Windows Runtime](/uwp/api/) proporciona los elementos de la interfaz de usuario para crear aplicaciones de la Tienda Windows 8.x, y proporciona acceso a las características del sistema operativo. Al igual que .NET Framework, Windows Runtime tiene metadatos que permiten a los compiladores de C# y de Visual Basic usar Windows Runtime de la misma forma en que usan las bibliotecas de clases de .NET Framework. .NET Framework hace que resulte mas fácil de utilizar Windows Runtime ocultando algunas diferencias:

  - Algunas diferencias en los patrones de programación entre .NET Framework y Windows Runtime, como el patrón para agregar y quitar controladores de eventos, están ocultas. Simplemente se usa el patrón de .NET Framework.

  - Algunas diferencias de tipos de uso general (por ejemplo, los tipos primitivos y las colecciones) están ocultas. Simplemente se usa el tipo de .NET Framework, como se describe en [Diferencias que son visibles en el IDE](#DifferencesVisibleInIDE), más adelante en este artículo.

La mayoría de las veces, la compatibilidad de .NET Framework con Windows Runtime es transparente. En la sección siguiente se describen algunas de las diferencias aparentes entre el código administrado y Windows Runtime.

<a name="AboutReferenceDocumentation"></a>

### <a name="the-net-framework-and-the-windows-runtime-reference-documentation"></a>Documentación de referencia sobre .NET Framework y Windows Runtime

Los conjuntos de documentación de Windows Runtime y .NET Framework son independientes. Si presiona F1 para mostrar la ayuda sobre un tipo o miembro, se muestra la documentación de referencia del conjunto correspondiente. Sin embargo, si examina la [Referencia de Windows Runtime](/uwp/api/), podría encontrar ejemplos que parecen desconcertantes:

- Algunos temas, como el relacionado con la interfaz <xref:Windows.Foundation.Collections.IIterable%601>, no tienen sintaxis de declaración para Visual Basic o C#. En su lugar, aparece una nota por encima de la sección de sintaxis (en este caso, ".NET: Esta interfaz aparece como System.Collections.Generic.IEnumerable\<T>"). Esto se debe a que .NET Framework y Windows Runtime proporcionan una funcionalidad similar con distintas interfaces. Además, hay diferencias de comportamiento: `IIterable` tiene un método `First` en lugar de un método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> para devolver el enumerador. En lugar de obligarle a que aprenda a realizar una tarea común de una manera diferente, .NET Framework admite Windows Runtime haciendo que parezca que su código administrado usa el tipo con el que está familiarizado. No verá la interfaz `IIterable` en el IDE, por lo que la única forma en que la encontrará en la documentación de referencia de Windows Runtime será cuando examine dicha documentación directamente.

- En la documentación de <xref:Windows.Web.Syndication.SyndicationFeed.%23ctor(System.String,System.String,Windows.Foundation.Uri)> se aprecia un problema bastante parecido: sus tipos de parámetros parecen distintos para los distintos idiomas. Para C# y Visual Basic, los tipos de parámetros son <xref:System.String?displayProperty=nameWithType> y <xref:System.Uri?displayProperty=nameWithType>. Esto también se debe a que .NET Framework tiene sus propios tipos `String` y `Uri`, y para esos tipos de uso tan general no tiene sentido obligar a los usuarios de .NET Framework a aprender una forma distinta de hacer las cosas. En el IDE, .NET Framework oculta los tipos correspondientes de Windows Runtime.

- En algunos casos, como el de la estructura <xref:Windows.UI.Xaml.GridLength>, .NET Framework proporciona un tipo con el mismo nombre pero con más funcionalidad. Por ejemplo, existe un conjunto de temas sobre constructores y propiedades relacionados con `GridLength`, pero solo tienen bloques de sintaxis para Visual Basic y C# porque los miembros solo están disponibles en el código administrado. En Windows Runtime, las estructuras solo tienen campos. La estructura de Windows Runtime requiere una clase auxiliar, <xref:Windows.UI.Xaml.GridLengthHelper>, para proporcionar una funcionalidad equivalente. No verá esa clase del asistente en el IDE cuando escriba código administrado.

- En el IDE, los tipos de Windows Runtime aparentemente se derivan de <xref:System.Object?displayProperty=nameWithType>. Parece que tienen miembros heredados de <xref:System.Object>, como <xref:System.Object.ToString%2A?displayProperty=nameWithType>. Estos miembros funcionan como lo harían si los tipos heredaran realmente de <xref:System.Object>, y los tipos de Windows Runtime pueden convertirse en <xref:System.Object>. Esta funcionalidad forma parte de la compatibilidad que proporciona .NET Framework con Windows Runtime. Sin embargo, si se consultan los tipos en la documentación de referencia de Windows Runtime, dichos miembros no aparecen. La documentación para estos miembros aparentemente heredados se proporciona en la documentación de referencia de <xref:System.Object?displayProperty=nameWithType>.

<a name="DifferencesVisibleInIDE"></a>

### <a name="differences-that-are-visible-in-the-ide"></a>Diferencias que son visibles en el IDE

En escenarios de programación más avanzados, como cuando se usa un componente de Windows Runtime escrito en C# para proporcionar la lógica de la aplicación para una aplicación de la Tienda Windows 8.x compilada para Windows mediante JavaScript, tales diferencias son evidentes tanto en el IDE como en la documentación. Cuando el componente devuelve una interfaz `IDictionary<int, string>` a JavaScript, si la examina en el depurador de JavaScript, verá los métodos de la interfaz `IMap<int, string>` porque JavaScript usa el tipo de Windows Runtime. Algunos tipos de colección de uso general que aparecen de manera diferente en los dos lenguajes se muestran en la tabla siguiente:

|Tipo de Windows en tiempo de ejecución|Tipo correspondiente de .NET Framework|
|--------------------------------------------------------------|---------------------------------------|
|`IIterable<T>`|`IEnumerable<T>`|
|`IIterator<T>`|`IEnumerator<T>`|
|`IVector<T>`|`IList<T>`|
|`IVectorView<T>`|`IReadOnlyList<T>`|
|`IMap<K, V>`|`IDictionary<TKey, TValue>`|
|`IMapView<K, V>`|`IReadOnlyDictionary<TKey, TValue>`|
|`IBindableIterable`|`IEnumerable`|
|`IBindableVector`|`IList`|
|`Windows.UI.Xaml.Data.INotifyPropertyChanged`|`System.ComponentModel.INotifyPropertyChanged`|
|`Windows.UI.Xaml.Data.PropertyChangedEventHandler`|`System.ComponentModel.PropertyChangedEventHandler`|
|`Windows.UI.Xaml.Data.PropertyChangedEventArgs`|`System.ComponentModel.PropertyChangedEventArgs`|

En Windows Runtime, `IMap<K, V>` y `IMapView<K, V>` se recorren en iteración mediante `IKeyValuePair`. Cuándo se pasan al código administrado, aparecen como `IDictionary<TKey, TValue>` e `IReadOnlyDictionary<TKey, TValue>`, por lo que naturalmente se usa `System.Collections.Generic.KeyValuePair<TKey, TValue>` para enumerarlas.

La forma en que las interfaces aparecen en código administrado afecta a la forma en que aparecen los tipos que implementan estas interfaces. Por ejemplo, la clase `PropertySet` implementa `IMap<K, V>`, que aparece en código administrado como `IDictionary<TKey, TValue>`. `PropertySet` aparece como si se implementara `IDictionary<TKey, TValue>` en lugar de `IMap<K, V>`, por lo que en código administrado parece tener un método `Add`, que se comporta como el método `Add` en diccionarios de .NET Framework. No parece tener un método `Insert`.

Para obtener más información sobre cómo usar .NET Framework para crear un componente de Windows Runtime y para consultar un tutorial donde se muestra cómo usar este componente con JavaScript, vea [Creación de componentes de Windows Runtime en C# y Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

### <a name="primitive-types"></a>Tipos primitivos

Para habilitar el uso natural de Windows Runtime en el código administrado, en el código aparecen los tipos primitivos de .NET Framework en lugar de los tipos primitivos de Windows Runtime. En .NET Framework, los tipos primitivos como la estructura `Int32` tienen muchas propiedades y métodos útiles, como el método `Int32.TryParse`. Por el contrario, los tipos primitivos y las estructuras de Windows Runtime solo tienen campos. Cuando se usan primitivas en el código administrado, aparecen como si fueran tipos de .NET Framework, y se pueden usar las propiedades y métodos de los tipos de .NET Framework como se haría normalmente. La lista siguiente contiene un resumen:

- Para los tipos primitivos de Windows Runtime `Int32`, `Int64`, `Single`, `Double`, `Boolean`, `String` (una colección inmutable de caracteres Unicode), `Enum`, `UInt32`, `UInt64` y `Guid`, use el tipo del mismo nombre en el espacio de nombres `System`.

- Para `UInt8`, utilice `System.Byte`.

- Para `Char16`, utilice `System.Char`.

- Para la interfaz `IInspectable`, use `System.Object`.

- Para `HRESULT`, use una estructura con un miembro `System.Int32`.

Como ocurre con los tipos de interfaz, la única ocasión en que puede ver una evidencia de esta representación es cuando el proyecto de .NET Framework es un componente de Windows Runtime utilizado por una aplicación de la Tienda Windows 8.x creada con JavaScript.

Otros tipos básicos de Windows Runtime que se usan con frecuencia y que aparecen en el código administrado como sus equivalentes de .NET Framework incluyen la estructura `Windows.Foundation.DateTime`, que aparece en el código administrado como la estructura <xref:System.DateTimeOffset?displayProperty=nameWithType>, y la estructura `Windows.Foundation.TimeSpan`, que aparece como la estructura <xref:System.TimeSpan?displayProperty=nameWithType>.

### <a name="other-differences"></a>Otras diferencias

En algunos casos, deberá realizar alguna acción para que aparezcan en el código los tipos de .NET Framework en lugar de los tipos de Windows Runtime. Por ejemplo, la clase <xref:Windows.Foundation.Uri?displayProperty=nameWithType> aparece como <xref:System.Uri?displayProperty=nameWithType> en el código de .NET Framework. <xref:System.Uri?displayProperty=nameWithType> permite un URI relativo, pero <xref:Windows.Foundation.Uri?displayProperty=nameWithType> requiere un URI absoluto. Por consiguiente, cuando pase un URI a un método de Windows Runtime, debe asegurarse de que sea absoluto. Consulta [Pasar un URI a Windows en tiempo de ejecución](passing-a-uri-to-the-windows-runtime.md).

<a name="WindowsRuntimeComponents"></a>

## <a name="scenarios-for-developing-windows-runtime-components"></a>Escenarios para el desarrollo de componentes de Windows en tiempo de ejecución

Los escenarios compatibles con los componentes administrados de Windows Runtime dependen de los principios generales siguientes:

- Los componentes de Windows Runtime creados con .NET Framework no tienen ninguna diferencia aparente respecto a otras bibliotecas de Windows Runtime. Por ejemplo, si vuelve a implementar un componente nativo de Windows Runtime mediante código administrado, en apariencia no existe ninguna diferencia entre los dos componentes. El hecho de que un componente esté escrito en código administrado es invisible para el código que lo utiliza, incluso si dicho código también es código administrado. Sin embargo, internamente, el componente es código administrado auténtico y se ejecuta en Common Language Runtime (CLR).

- Los componentes pueden contener tipos que implementan la lógica de la aplicación, controles de la interfaz de usuario de la Tienda Windows 8.x, o ambos.

  > [!NOTE]
  > Es recomendable separar los elementos de la interfaz de usuario de la lógica de la aplicación. Además, no se pueden usar controles de la interfaz de usuario de la Tienda Windows 8.x en una aplicación de la Tienda Windows 8.x compilada para Windows con JavaScript y HTML.

- Un componente puede ser un proyecto de una solución de Visual Studio para una aplicación de la Tienda Windows 8.x o un componente reutilizable que se puede agregar a varias soluciones.

  > [!NOTE]
  > Si un componente solo se va a usar con C# o Visual Basic, no hay ninguna razón para convertirlo en un componente de Windows Runtime. Si en lugar de ello se crea una biblioteca de clases de .NET Framework ordinaria, no será necesario restringir la superficie de la API pública a los tipos de Windows Runtime.

- Se pueden lanzar versiones de componentes reutilizables mediante el uso del atributo <xref:Windows.Foundation.Metadata.VersionAttribute> de Windows Runtime para identificar qué tipos y qué miembros dentro de un tipo se agregaron en las distintas versiones.

- Los tipos del componente se pueden derivar de los tipos de Windows Runtime. Los controles pueden derivarse de los tipos de control primitivos en el espacio de nombres <xref:Windows.UI.Xaml.Controls.Primitives> o de controles más terminados, como <xref:Windows.UI.Xaml.Controls.Button>.

  > [!IMPORTANT]
  > A partir de Windows 8 y .NET Framework 4.5, todos los tipos públicos de un componente de Windows Runtime administrado deben estar sellados. Un tipo de otro componente de Windows Runtime no puede derivarse de ellos. Si se desea proporcionar un comportamiento polimórfico a un componente, puede crear una interfaz e implementarla en los tipos polimórficos.

- Todos los parámetros y tipos devueltos de los tipos públicos del componente deben ser tipos de Windows Runtime (incluidos los tipos de Windows Runtime definidos por el componente).

En las secciones siguientes se proporcionan ejemplos de escenarios comunes.

### <a name="application-logic-for-a-windows-8x-store-app-with-javascript"></a>Lógica de aplicación para una aplicación de la Tienda Windows 8.x con JavaScript

Al desarrollar una aplicación de la Tienda Windows 8.x para Windows mediante JavaScript, puede que algunas partes de la lógica de la aplicación funcionen mejor en código administrado, o que sean más fáciles de desarrollar. JavaScript no puede utilizar las bibliotecas de clases de .NET Framework directamente, pero puede convertir la biblioteca de clases en un archivo .WinMD. En este escenario, el componente de Windows Runtime es una parte integral de la aplicación, por lo que no tiene sentido proporcionar atributos de versión.

### <a name="reusable-windows-8x-store-ui-controls"></a>Controles de la interfaz de usuario de la Tienda Windows 8.x reutilizables

Se puede empaquetar un conjunto de controles relacionados de la interfaz de usuario en un componente reutilizable de Windows Runtime. El componente se puede comercializar por separado o usarse como elemento de las aplicaciones que se creen. En este escenario, tiene sentido usar el atributo <xref:Windows.Foundation.Metadata.VersionAttribute> de Windows Runtime para mejorar la compatibilidad.

### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>Lógica de aplicación reutilizable de aplicaciones existentes de .NET Framework

Se puede empaquetar código administrado de aplicaciones de escritorio existentes como un componente independiente de Windows Runtime. Esto permite usar el componente en las aplicaciones de la Tienda Windows 8.x creadas con C++ o JavaScript, así como en las aplicaciones de la Tienda Windows 8.x creadas con C# o Visual Basic. El control de versiones es una opción si existen varios escenarios de reutilización para el código.

## <a name="related-topics"></a>Temas relacionados

|Title|Descripción|
|-----------|-----------------|
|[Información general de .NET para aplicaciones de la Tienda Windows](/previous-versions/windows/apps/br230302(v=vs.140))|Se describen los tipos y miembros de .NET Framework que se pueden usar para crear aplicaciones de la Tienda Windows 8.x y componentes de Windows Runtime. (En el Centro de desarrollo de Windows).|
|[Guía básica para crear aplicaciones de la Tienda Windows con C# o Visual Basic](/previous-versions/windows/apps/br229583(v=win.10))|Se proporcionan recursos clave para ayudarle a empezar a desarrollar aplicaciones de la Tienda Windows 8.x mediante C# o Visual Basic, y se incluyen numerosos tutoriales rápidos, directrices y procedimientos recomendados. (En el Centro de desarrollo de Windows).|
|[Procedimientos (XAML)](/previous-versions/windows/apps/br229566(v=win.10))|Se proporcionan recursos clave para ayudarle a empezar a desarrollar aplicaciones de la Tienda Windows 8.x mediante C# o Visual Basic, y se incluyen numerosos tutoriales rápidos, directrices y procedimientos recomendados. (En el Centro de desarrollo de Windows).|
|[Crear componentes de Windows en tiempo de ejecución en C# y Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)|Se describe cómo crear un componente de Windows Runtime mediante .NET Framework, se explica cómo usarlo como parte de una aplicación de la Tienda Windows 8.x creada para Windows mediante JavaScript y se describe cómo depurar la combinación con Visual Studio. (En el Centro de desarrollo de Windows).|
|[Referencia de Windows Runtime](/uwp/api/)|Documentación de referencia para Windows Runtime. (En el Centro de desarrollo de Windows).|
|[Passing a URI to the Windows Runtime](passing-a-uri-to-the-windows-runtime.md) (Transferencia de un URI a Windows Runtime)|Se describe un problema que puede surgir cuando se pasa un URI desde el código administrado a Windows Runtime y cómo evitarlo.|
