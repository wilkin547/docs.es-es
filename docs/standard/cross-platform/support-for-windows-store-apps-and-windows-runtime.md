---
title: Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows en tiempo de ejecución
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Windows Store apps, .NET Framework support for
- Windows Runtime, .NET Framework support for
- .NET for Windows Store apps
- .NET Framework, and Windows Store apps
- .NET Framework, and Windows Runtime
ms.assetid: 6fa7d044-ae12-4c54-b8ee-50915607a565
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a51d8d77318685e4a4c8b90a793f2946de4a792b
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025543"
---
# <a name="net-framework-support-for-windows-store-apps-and-windows-runtime"></a>Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows en tiempo de ejecución
.NET Framework 4.5 admite una serie de escenarios de desarrollo de software con el tiempo de ejecución de Windows. Estos escenarios se clasifican en tres categorías:

- Desarrollar [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicaciones con los controles XAML, como se describe en [aplicaciones Guía básica para Windows Store usando C# o Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10)), [cómo tos (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10)), y [información general de aplicaciones de .NET para Windows Store ](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)).

- Desarrollo de bibliotecas de clases para su uso en aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] creadas con .NET Framework.

- Desarrollar componentes de Windows en tiempo de ejecución, empaquetado en. Archivos de WinMD, pueden usar cualquier lenguaje de programación que admita el tiempo de ejecución de Windows. Por ejemplo, vea [crear componentes de Windows en tiempo de ejecución en C# y Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

 En este tema se describe la compatibilidad que .NET Framework proporciona para las tres categorías y se describen los escenarios para los componentes de Windows en tiempo de ejecución. La primera sección incluye información básica sobre la relación entre .NET Framework y el tiempo de ejecución de Windows y explica algunas singularidades que pueden surgir en el sistema de ayuda y el IDE. El [segunda sección](#WindowsRuntimeComponents) se describen los escenarios para desarrollar componentes de Windows en tiempo de ejecución.

## <a name="the-basics"></a>Conceptos básicos
 .NET Framework admite los tres escenarios de desarrollo indicados anteriormente proporcionando [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]y admitiendo el propio tiempo de ejecución de Windows.

- [Los espacios de nombres de .NET framework y Windows Runtime](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)#net-framework-and-windows-runtime-namespaces) proporciona una vista simplificada de las bibliotecas de clases de .NET Framework e incluyen sólo los tipos y miembros que se puede utilizar para crear [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicaciones y componentes de Windows en tiempo de ejecución.

    - Cuando usa Visual Studio (Visual Studio 2012 o posterior) para desarrollar un [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicación o un componente de Windows Runtime, un conjunto de ensamblados de referencia garantiza que vea únicamente los tipos y miembros relevantes.

    - Este conjunto racionalizado de API se simplifica aún más las características mediante la eliminación de las características que son duplicados dentro de .NET Framework o que duplican en tiempo de ejecución de Windows. Por ejemplo, contiene solo las versiones genéricas de tipos de colección, y el modelo de objetos de documento XML se ha eliminado en favor de la API de Windows en tiempo de ejecución XML establecido.

    - También se quitan las características que simplemente encapsulan la API del sistema operativo, porque el tiempo de ejecución de Windows es fácil llamar desde código administrado.

     Para obtener más información sobre la [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], consulte el [información general de aplicaciones de .NET para Windows Store](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)). Para obtener información sobre el proceso de selección de API, consulte el [.NET para aplicaciones estilo Metro](https://devblogs.microsoft.com/dotnet/net-for-metro-style-apps/) entrada del blog. NET.

- El [en tiempo de ejecución de Windows](/uwp/api/) proporciona elementos de interfaz de usuario para la compilación [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] las aplicaciones y proporciona acceso a características del sistema operativo. Al igual que .NET Framework, el tiempo de ejecución de Windows tiene metadatos que permiten la C# y las bibliotecas de clases de compiladores de Visual Basic para usar el Runtime de Windows de la forma en la que usan .NET Framework. .NET Framework hace más fácil de usar el tiempo de ejecución de Windows ocultando algunas diferencias:

    - Algunas diferencias en los patrones de programación entre .NET Framework y el tiempo de ejecución de Windows, como el patrón para agregar y quitar controladores de eventos, están ocultos. Simplemente se usa el patrón de .NET Framework.

    - Algunas diferencias de tipos de uso general (por ejemplo, los tipos primitivos y las colecciones) están ocultas. Usar simplemente el tipo de .NET Framework, como se describe en [diferencias que son visibles en el IDE](#DifferencesVisibleInIDE), más adelante en este artículo.

 La mayoría de los casos, la compatibilidad de .NET Framework para el tiempo de ejecución de Windows es transparente. La siguiente sección describe algunas de las diferencias aparentes entre código administrado y el tiempo de ejecución de Windows.

<a name="AboutReferenceDocumentation"></a>
### <a name="the-net-framework-and-the-windows-runtime-reference-documentation"></a>.NET Framework y la documentación de referencia en tiempo de ejecución de Windows
 El tiempo de ejecución de Windows y los conjuntos de documentación de .NET Framework son independientes. Si presiona F1 para mostrar la ayuda sobre un tipo o miembro, se muestra la documentación de referencia del conjunto correspondiente. Sin embargo, si examina el [referencia en tiempo de ejecución de Windows](/uwp/api/) , podría encontrar ejemplos que parecen desconcertantes:

- Algunos temas, como el <xref:Windows.Foundation.Collections.IIterable%601> interfaz no tiene la sintaxis de declaración para Visual Basic o C#. En su lugar, aparece una nota por encima de la sección de sintaxis (en este caso, ". NET: Esta interfaz aparece como System.Collections.Generic.IEnumerable\<T > "). Esto es porque el tiempo de ejecución de Windows y de .NET Framework proporcionan una funcionalidad similar con distintas interfaces. Además, hay diferencias de comportamiento: `IIterable` tiene un método `First` en lugar de un método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> para devolver el enumerador. En lugar de obligarle a aprender una forma distinta de llevar a cabo una tarea común, .NET Framework admite el tiempo de ejecución de Windows mediante la realización de aparecer al usar el tipo que está familiarizado con el código administrado. No verá el `IIterable` interfaz en el IDE y, por lo tanto, la única forma que encontrará en la documentación de referencia en tiempo de ejecución de Windows es examine dicha documentación directamente.

- El <xref:Windows.Web.Syndication.SyndicationFeed.%23ctor(System.String,System.String,Windows.Foundation.Uri)> documentación ilustra un problema: Sus tipos de parámetros parecen distintos para diferentes idiomas. Para C# y Visual Basic, los tipos de parámetros son <xref:System.String?displayProperty=nameWithType> y <xref:System.Uri?displayProperty=nameWithType>. Esto también se debe a que .NET Framework tiene sus propios tipos `String` y `Uri`, y para esos tipos de uso tan general no tiene sentido obligar a los usuarios de .NET Framework a aprender una forma distinta de hacer las cosas. En el IDE, .NET Framework oculta los tipos en tiempo de ejecución de Windows correspondientes.

- En algunos casos, como el <xref:Windows.UI.Xaml.GridLength> estructura, .NET Framework proporciona un tipo con el mismo nombre pero con más funcionalidad. Por ejemplo, existe un conjunto de temas sobre constructores y propiedades relacionados con `GridLength`, pero solo tienen bloques de sintaxis para Visual Basic y C# porque los miembros solo están disponibles en el código administrado. En el tiempo de ejecución de Windows, las estructuras solo tienen campos. La estructura de tiempo de ejecución de Windows requiere una clase auxiliar, <xref:Windows.UI.Xaml.GridLengthHelper>, para proporcionar una funcionalidad equivalente. No verá esa clase del asistente en el IDE cuando escriba código administrado.

- En el IDE, los tipos de Windows Runtime aparecen se derivan de <xref:System.Object?displayProperty=nameWithType>. Parece que tienen miembros heredados de <xref:System.Object>, como <xref:System.Object.ToString%2A?displayProperty=nameWithType>. Estos miembros funcionan como lo harían si los tipos heredaran realmente de <xref:System.Object>, y los tipos en tiempo de ejecución de Windows se pueden convertir en <xref:System.Object>. Esta funcionalidad forma parte de la compatibilidad que .NET Framework proporciona para el tiempo de ejecución de Windows. Sin embargo, si ve los tipos en la documentación de referencia en tiempo de ejecución de Windows, dichos miembros no aparecen. La documentación para estos miembros aparentemente heredados se proporciona en la documentación de referencia de <xref:System.Object?displayProperty=nameWithType>.

<a name="DifferencesVisibleInIDE"></a>
### <a name="differences-that-are-visible-in-the-ide"></a>Diferencias que son visibles en el IDE
 En escenarios de programación, como el uso de un componente de Windows en tiempo de ejecución escrito en más avanzados C# para proporcionar la lógica de aplicación para un [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicación compilada para Windows con JavaScript, tales diferencias son evidentes en el IDE, así como en el documentación. Cuando el componente devuelve un `IDictionary<int, string>` a JavaScript y, mire en el depurador de JavaScript, podrá ver los métodos de `IMap<int, string>` porque JavaScript usa el tipo en tiempo de ejecución de Windows. Algunos tipos de colección de uso general que aparecen de manera diferente en los dos lenguajes se muestran en la tabla siguiente:

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

 En el tiempo de ejecución de Windows, `IMap<K, V>` y `IMapView<K, V>` se recorren en iteración mediante `IKeyValuePair`. Cuándo se pasan al código administrado, aparecen como `IDictionary<TKey, TValue>` e `IReadOnlyDictionary<TKey, TValue>`, por lo que naturalmente se usa `System.Collections.Generic.KeyValuePair<TKey, TValue>` para enumerarlas.

 La forma en que las interfaces aparecen en código administrado afecta a la forma en que aparecen los tipos que implementan estas interfaces. Por ejemplo, la clase `PropertySet` implementa `IMap<K, V>`, que aparece en código administrado como `IDictionary<TKey, TValue>`. `PropertySet` aparece como si se implementara `IDictionary<TKey, TValue>` en lugar de `IMap<K, V>`, por lo que en código administrado parece tener un método `Add`, que se comporta como el método `Add` en diccionarios de .NET Framework. No parece tener un método `Insert`.

 Para obtener más información sobre el uso de .NET Framework para crear un componente de Windows Runtime y un tutorial que muestra cómo usar este componente con JavaScript, consulte [crear componentes de Windows en tiempo de ejecución en C# y Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

### <a name="primitive-types"></a>Tipos primitivos
 Para habilitar el uso natural de Windows Runtime en código administrado, aparecen los tipos primitivos de .NET Framework en lugar de tipos primitivos de Windows en tiempo de ejecución en el código. En .NET Framework, los tipos primitivos como la estructura `Int32` tienen muchas propiedades y métodos útiles, como el método `Int32.TryParse`. Por el contrario, los tipos primitivos y las estructuras en el tiempo de ejecución de Windows solo tienen campos. Cuando se usan primitivas en el código administrado, aparecen como si fueran tipos de .NET Framework, y se pueden usar las propiedades y métodos de los tipos de .NET Framework como se haría normalmente. La lista siguiente contiene un resumen:

- Para las primitivas de Windows en tiempo de ejecución `Int32`, `Int64`, `Single`, `Double`, `Boolean`, `String` (una colección inmutable de caracteres Unicode), `Enum`, `UInt32`, `UInt64`, y `Guid`, utilice el tipo del mismo nombre en el `System` espacio de nombres.

- Para `UInt8`, use `System.Byte`.

- Para `Char16`, use `System.Char`.

- Para la interfaz `IInspectable`, use `System.Object`.

- Para `HRESULT`, use una estructura con un miembro `System.Int32`.

 Como con tipos de interfaz, la única vez que podría ver la evidencia de esta representación es cuando el proyecto de .NET Framework es un componente de tiempo de ejecución de Windows que está usando un [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicación compilada con JavaScript.

 Otros tipos de Windows en tiempo de ejecución básicas y usadas que aparecen en el código administrado como sus equivalentes de .NET Framework incluyen la `Windows.Foundation.DateTime` estructura, que aparece en código administrado como el <xref:System.DateTimeOffset?displayProperty=nameWithType> estructura y el `Windows.Foundation.TimeSpan` estructura que aparece como el <xref:System.TimeSpan?displayProperty=nameWithType> estructura.

### <a name="other-differences"></a>Otras diferencias
 En algunos casos, el hecho de que los tipos de .NET Framework aparecen en el código en lugar de tipos en tiempo de ejecución de Windows requiere acción por parte del usuario. Por ejemplo, el <xref:Windows.Foundation.Uri?displayProperty=nameWithType> clase aparece como <xref:System.Uri?displayProperty=nameWithType> en el código de .NET Framework. <xref:System.Uri?displayProperty=nameWithType> permite un URI relativo, pero <xref:Windows.Foundation.Uri?displayProperty=nameWithType> requiere un URI absoluto. Por lo tanto, cuando se pasa un URI a un método en tiempo de ejecución de Windows, debe asegurarse de que es absoluta. (Consulte [pasar un URI a Windows Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md).)

<a name="WindowsRuntimeComponents"></a>
## <a name="scenarios-for-developing-windows-runtime-components"></a>Escenarios para el desarrollo de componentes de Windows en tiempo de ejecución
 Los escenarios que son compatibles con los componentes administrados de Windows en tiempo de ejecución dependen de los siguientes principios generales:

- Los componentes de Windows en tiempo de ejecución que se compilan con .NET Framework no tienen ninguna diferencia aparente de otras Runtimelibraries de Windows. Por ejemplo, si se volver a implementa un componente en tiempo de ejecución de Windows nativo con código administrado, los dos componentes son indistinguibles hacia afuera. El hecho de que un componente esté escrito en código administrado es invisible para el código que lo utiliza, incluso si dicho código también es código administrado. Sin embargo, internamente, el componente es código administrado auténtico y se ejecuta en Common Language Runtime (CLR).

- Los componentes pueden contener tipos que implementan la lógica de la aplicación, controles de la interfaz de usuario de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] o ambos.

    > [!NOTE]
    >  Es recomendable separar los elementos de la interfaz de usuario de la lógica de la aplicación. Además, no se pueden usar controles de la interfaz de usuario de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] en una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] creada para Windows mediante JavaScript y HTML.

- Un componente puede ser un proyecto de una solución de Visual Studio para una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] o un componente reutilizable que se puede agregar a varias soluciones.

    > [!NOTE]
    >  Si el componente se utiliza únicamente con C# o Visual Basic, no hay ninguna razón para convertirlo en un componente de Windows en tiempo de ejecución. Si hace que sea una biblioteca de clases de .NET Framework ordinaria en su lugar, no tienes que restringen su superficie de API pública a los tipos en tiempo de ejecución de Windows.

- Puede liberar las versiones de componentes reutilizables mediante el entorno de ejecución de Windows <xref:Windows.Foundation.Metadata.VersionAttribute> atributo para identificar qué tipos (y qué miembros dentro de un tipo) se agregaron en versiones diferentes.

- Los tipos en el componente pueden derivar de tipos en tiempo de ejecución de Windows. Los controles pueden derivarse de los tipos de controles primitivos del <xref:Windows.UI.Xaml.Controls.Primitives> espacio de nombres o de varios controles, como <xref:Windows.UI.Xaml.Controls.Button>.

    > [!IMPORTANT]
    >  A partir de [!INCLUDE[win8](../../../includes/win8-md.md)] y .NET Framework 4.5, todos los tipos públicos de un componente administrado de Windows en tiempo de ejecución deben estar selladas. Un tipo en otro componente en tiempo de ejecución de Windows no puede derivar de ellas. Si se desea proporcionar un comportamiento polimórfico a un componente, puede crear una interfaz e implementarla en los tipos polimórficos.

- Todos los parámetros y tipos devueltos en los tipos públicos del componente deben ser tipos de tiempo de ejecución de Windows (incluidos los tipos en tiempo de ejecución de Windows que define el componente).

 En las secciones siguientes se proporcionan ejemplos de escenarios comunes.

### <a name="application-logic-for-a-includewin8appnamelongincludeswin8-appname-long-mdmd-app-with-javascript"></a>Lógica de aplicación para una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] con JavaScript
 Al desarrollar una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] para Windows mediante JavaScript, puede que algunas partes de la lógica de la aplicación funcionen mejor en código administrado, o que sean más fáciles de desarrollar. JavaScript no puede utilizar las bibliotecas de clases de .NET Framework directamente, pero puede convertir la biblioteca de clases en un archivo .WinMD. En este escenario, el componente de tiempo de ejecución de Windows es una parte integral de la aplicación, por lo que no tiene sentido proporcionar atributos de versión.

### <a name="reusable-includewin8appnamelongincludeswin8-appname-long-mdmd-ui-controls"></a>Controles reutilizables de la interfaz de usuario de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]
 Puede empaquetar un conjunto de controles de interfaz de usuario relacionados en un componente reutilizable de Windows en tiempo de ejecución. El componente se puede comercializar por separado o usarse como elemento de las aplicaciones que se creen. En este escenario, tiene sentido usar el Runtime de Windows <xref:Windows.Foundation.Metadata.VersionAttribute> atributo para mejorar la compatibilidad.

### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>Lógica de aplicación reutilizable de aplicaciones existentes de .NET Framework
 Puede empaquetar código administrado desde las aplicaciones de escritorio existentes como un componente de Windows en tiempo de ejecución independiente. Esto permite usar el componente en las aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] creadas con C++ o JavaScript, así como en las aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] creadas con C# o Visual Basic. El control de versiones es una opción si existen varios escenarios de reutilización para el código.

## <a name="related-topics"></a>Temas relacionados

|Título|Descripción|
|-----------|-----------------|
|[Información general de .NET para aplicaciones de la Tienda Windows](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140))|Describe los tipos de .NET Framework y los miembros que se pueden utilizar para crear [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] RuntimeComponents de Windows y aplicaciones. (En el Centro de desarrollo de Windows).|
|[Guía básica para aplicaciones de Windows Store usando C# o Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10))|Proporciona recursos clave para ayudarle a empezar a desarrollar aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] mediante C# o Visual Basic, e incluye numerosos tutoriales rápidos, directrices y procedimientos recomendados. (En el Centro de desarrollo de Windows).|
|[Cómo tos (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))|Proporciona recursos clave para ayudarle a empezar a desarrollar aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] mediante C# o Visual Basic, e incluye numerosos tutoriales rápidos, directrices y procedimientos recomendados. (En el Centro de desarrollo de Windows).|
|[Crear componentes de Windows en tiempo de ejecución en C# y Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)|Describe cómo crear un componente de tiempo de ejecución de Windows mediante .NET Framework, explica cómo se usa como parte de un [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicación compilado para Windows con JavaScript y se describe cómo depurar la combinación con Visual Studio. (En el Centro de desarrollo de Windows).|
|[Referencia de Windows en tiempo de ejecución](/uwp/api/)|La documentación de referencia para el tiempo de ejecución de Windows. (En el Centro de desarrollo de Windows).|
|[Transferencia de un URI a Windows Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md)|Describe un problema que puede surgir cuando se pasa un URI desde el código administrado para el tiempo de ejecución de Windows y cómo evitar esta situación.|
