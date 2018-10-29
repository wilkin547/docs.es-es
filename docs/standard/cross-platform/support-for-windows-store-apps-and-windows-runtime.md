---
title: Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime
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
ms.openlocfilehash: 0476fe7ed731dbb2c6b86cff3255673ecee6f98d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198463"
---
# <a name="net-framework-support-for-windows-store-apps-and-windows-runtime"></a>Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] admite varios escenarios de desarrollo de software con [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Estos escenarios se clasifican en tres categorías:

-   Desarrollar [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicaciones con los controles XAML, como se describe en [aplicaciones Guía básica para Windows Store usando C# o Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10)), [cómo tos (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10)), y [información general de aplicaciones de .NET para Windows Store ](https://msdn.microsoft.com/library/windows/apps/br230302%28v=VS.110%29.aspx).

-   Desarrollo de bibliotecas de clases para su uso en aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] creadas con .NET Framework.

-   Desarrollo de componentes de [!INCLUDE[wrt](../../../includes/wrt-md.md)], empaquetados en archivos .WinMD, que se pueden usar en cualquier lenguaje de programación que admita [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Por ejemplo, vea [crear componentes de Windows en tiempo de ejecución en C# y Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

 En este tema se describe la compatibilidad que proporciona .NET Framework para las tres categorías y se describen los escenarios para los componentes de [!INCLUDE[wrt](../../../includes/wrt-md.md)]. En la primera sección se incluye información básica sobre la relación entre .NET Framework y [!INCLUDE[wrt](../../../includes/wrt-md.md)], y se explican algunas singularidades que se pueden encontrar en el sistema de ayuda y el IDE. El [segunda sección](#WindowsRuntimeComponents) se describen los escenarios para desarrollar [!INCLUDE[wrt](../../../includes/wrt-md.md)] componentes.

## <a name="the-basics"></a>Conceptos básicos
 .NET Framework admite los tres escenarios de desarrollo indicados anteriormente proporcionando [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] y admitiendo el propio [!INCLUDE[wrt](../../../includes/wrt-md.md)].

-   [Las aplicaciones de .NET para Windows Store](https://msdn.microsoft.com/library/windows/apps/br230232(v=vs.110).aspx) proporciona una vista simplificada de las bibliotecas de clases de .NET Framework e incluyen sólo los tipos y miembros que se puede utilizar para crear [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicaciones y [!INCLUDE[wrt](../../../includes/wrt-md.md)] componentes.

    -   Cuando usa Visual Studio (Visual Studio 2012 o posterior) para desarrollar un [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicación o un [!INCLUDE[wrt](../../../includes/wrt-md.md)] componente, un conjunto de ensamblados de referencia garantiza que vea únicamente los tipos y miembros relevantes.

    -   Este conjunto racionalizado de API se simplifica aún más mediante la supresión de las características duplicadas en .NET Framework o que duplican características de [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Por ejemplo, solo contiene las versiones genéricas de los tipos de colección, y se ha eliminado el modelo de objetos de documento XML a favor del conjunto de API de XML de [!INCLUDE[wrt](../../../includes/wrt-md.md)].

    -   También se han eliminado las características que simplemente encapsulan la API del sistema operativo, porque resulta sencillo llamar a [!INCLUDE[wrt](../../../includes/wrt-md.md)] desde el código administrado.

     Para obtener más información sobre la [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], consulte el [información general de aplicaciones de .NET para Windows Store](https://msdn.microsoft.com/library/windows/apps/br230302(v=VS.110).aspx). Para obtener información sobre el proceso de selección de API, consulte el [.NET para aplicaciones estilo Metro](https://blogs.msdn.microsoft.com/dotnet/2012/04/17/net-for-metro-style-apps/) entrada del blog. NET.

-   El [en tiempo de ejecución de Windows](/uwp/api/) proporciona elementos de interfaz de usuario para la compilación [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] las aplicaciones y proporciona acceso a características del sistema operativo. Al igual que .NET Framework, [!INCLUDE[wrt](../../../includes/wrt-md.md)] tiene metadatos que permiten a los compiladores de C# y de Visual Basic usar [!INCLUDE[wrt](../../../includes/wrt-md.md)] de la misma forma en que usan las bibliotecas de clases de .NET Framework. .NET Framework hace que resulte mas fácil de utilizar [!INCLUDE[wrt](../../../includes/wrt-md.md)] ocultando algunas diferencias:

    -   Algunas diferencias en los patrones de programación entre .NET Framework y [!INCLUDE[wrt](../../../includes/wrt-md.md)], como el patrón para agregar y quitar controladores de eventos, están ocultas. Simplemente se usa el patrón de .NET Framework.

    -   Algunas diferencias de tipos de uso general (por ejemplo, los tipos primitivos y las colecciones) están ocultas. Usar simplemente el tipo de .NET Framework, como se describe en [diferencias que son visibles en el IDE](#DifferencesVisibleInIDE), más adelante en este artículo.

 La mayoría de las veces, la compatibilidad de .NET Framework [!INCLUDE[wrt](../../../includes/wrt-md.md)] es transparente. En la sección siguiente se describen algunas de las diferencias aparentes entre el código administrado y [!INCLUDE[wrt](../../../includes/wrt-md.md)].

<a name="AboutReferenceDocumentation"></a>
### <a name="the-net-framework-and-the-includewrtincludeswrt-mdmd-reference-documentation"></a>.NET Framework y la documentación de referencia de [!INCLUDE[wrt](../../../includes/wrt-md.md)]
 El tiempo de ejecución de Windows y los conjuntos de documentación de .NET Framework son independientes. Si presiona F1 para mostrar la ayuda sobre un tipo o miembro, se muestra la documentación de referencia del conjunto correspondiente. Sin embargo, si examina el [referencia en tiempo de ejecución de Windows](/uwp/api/) , podría encontrar ejemplos que parecen desconcertantes:

-   Algunos temas, como el <xref:Windows.Foundation.Collections.IIterable%601> interfaz no tiene la sintaxis de declaración para Visual Basic o C#. En su lugar, aparece una nota por encima de la sección de sintaxis (en este caso, ".NET: esta interfaz aparece como System.Collections.Generic.IEnumerable\<T >"). Esto se debe a que .NET Framework y [!INCLUDE[wrt](../../../includes/wrt-md.md)] proporcionan una funcionalidad similar con distintas interfaces. Además, hay diferencias de comportamiento: `IIterable` tiene un método `First` en lugar de un método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> para devolver el enumerador. En lugar de obligarle a que aprenda a realizar una tarea común de una manera diferente, .NET Framework admite [!INCLUDE[wrt](../../../includes/wrt-md.md)] haciendo que parezca que su código administrado usa el tipo con el que está familiarizado. No verá la interfaz `IIterable` en el IDE, por lo que la única forma en que la encontrará en la documentación de referencia de [!INCLUDE[wrt](../../../includes/wrt-md.md)] será cuando examine dicha documentación directamente.

-   El <xref:Windows.Web.Syndication.SyndicationFeed.%23ctor(System.String,System.String,Windows.Foundation.Uri)> documentación ilustra un problema: sus tipos de parámetros parecen distintos para diferentes idiomas. Para C# y Visual Basic, los tipos de parámetros son <xref:System.String?displayProperty=nameWithType> y <xref:System.Uri?displayProperty=nameWithType>. Esto también se debe a que .NET Framework tiene sus propios tipos `String` y `Uri`, y para esos tipos de uso tan general no tiene sentido obligar a los usuarios de .NET Framework a aprender una forma distinta de hacer las cosas. En el IDE, .NET Framework oculta los tipos correspondientes de [!INCLUDE[wrt](../../../includes/wrt-md.md)].

-   En algunos casos, como el <xref:Windows.UI.Xaml.GridLength> estructura, .NET Framework proporciona un tipo con el mismo nombre pero con más funcionalidad. Por ejemplo, existe un conjunto de temas sobre constructores y propiedades relacionados con `GridLength`, pero solo tienen bloques de sintaxis para Visual Basic y C# porque los miembros solo están disponibles en el código administrado. En [!INCLUDE[wrt](../../../includes/wrt-md.md)], las estructuras solo tienen campos. El [!INCLUDE[wrt](../../../includes/wrt-md.md)] estructura requiere una clase auxiliar, <xref:Windows.UI.Xaml.GridLengthHelper>, para proporcionar una funcionalidad equivalente. No verá esa clase del asistente en el IDE cuando escriba código administrado.

-   En el IDE, los tipos de [!INCLUDE[wrt](../../../includes/wrt-md.md)] aparentemente se derivan de <xref:System.Object?displayProperty=nameWithType>. Parece que tienen miembros heredados de <xref:System.Object>, como <xref:System.Object.ToString%2A?displayProperty=nameWithType>. Estos miembros funcionan como lo harían si los tipos heredaran realmente de <xref:System.Object>, y los tipos de [!INCLUDE[wrt](../../../includes/wrt-md.md)] pueden convertirse en <xref:System.Object>. Esta funcionalidad forma parte de la compatibilidad que proporciona .NET Framework para [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Sin embargo, si se consultan los tipos en la documentación de referencia de [!INCLUDE[wrt](../../../includes/wrt-md.md)], dichos miembros no aparecen. La documentación para estos miembros aparentemente heredados se proporciona en la documentación de referencia de <xref:System.Object?displayProperty=nameWithType>.

<a name="DifferencesVisibleInIDE"></a>
### <a name="differences-that-are-visible-in-the-ide"></a>Diferencias que son visibles en el IDE
 En escenarios de programación más avanzados, como cuando se usa un componente de [!INCLUDE[wrt](../../../includes/wrt-md.md)] escrito en C# para proporcionar la lógica de la aplicación para una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] compilada para Windows mediante JavaScript, tales diferencias son evidentes tanto en el IDE como en la documentación. Cuando el componente devuelve una interfaz `IDictionary<int, string>` a JavaScript, si la examina en el depurador de JavaScript, verá los métodos de la interfaz `IMap<int, string>` porque JavaScript usa el tipo de [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Algunos tipos de colecciones de uso general que aparecen de manera diferente en los dos lenguajes se muestran en la tabla siguiente:

|Tipo de [!INCLUDE[wrt](../../../includes/wrt-md.md)]|Tipo correspondiente de .NET Framework|
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

 En [!INCLUDE[wrt](../../../includes/wrt-md.md)], `IMap<K, V>` e `IMapView<K, V>` se recorren en iteración mediante `IKeyValuePair`. Cuando las pasas a código administrado, aparecen como `IDictionary<TKey, TValue>` y `IReadOnlyDictionary<TKey, TValue>`, por lo que utilizas `System.Collections.Generic.KeyValuePair<TKey, TValue>` naturalmente para enumerarlas.

 La forma en que aparecen las interfaces en el código administrado afecta a la forma en que aparecen los tipos que implementan estas interfaces. Por ejemplo, la clase `PropertySet` implementa `IMap<K, V>`, que aparece en código administrado como `IDictionary<TKey, TValue>`. `PropertySet` aparece como si se implementara `IDictionary<TKey, TValue>` en lugar de `IMap<K, V>`, por lo que en código administrado parece tener un método `Add`, que se comporta como el método `Add` en diccionarios de .NET Framework. No parece tener un método `Insert`.

 Para obtener más información sobre el uso de .NET Framework para crear un [!INCLUDE[wrt](../../../includes/wrt-md.md)] componente y un tutorial que muestra cómo usar este componente con JavaScript, vea [crear componentes de Windows en tiempo de ejecución en C# y Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

### <a name="primitive-types"></a>Tipos primitivos
 Para habilitar el uso natural de [!INCLUDE[wrt](../../../includes/wrt-md.md)] en el código administrado, en el código aparecen los tipos primitivos de .NET Framework en lugar de los tipos primitivos de [!INCLUDE[wrt](../../../includes/wrt-md.md)]. En .NET Framework, los tipos primitivos como la estructura `Int32` tienen muchas propiedades y métodos útiles, como el método `Int32.TryParse`. Por el contrario, los tipos primitivos y las estructuras de [!INCLUDE[wrt](../../../includes/wrt-md.md)] solo tienen campos. Cuando se usan primitivas en el código administrado, aparecen como si fueran tipos de .NET Framework, y se pueden usar las propiedades y métodos de los tipos de .NET Framework como se haría normalmente. La lista siguiente contiene un resumen:

-   Para las primitivas de [!INCLUDE[wrt](../../../includes/wrt-md.md)]`Int32`, `Int64`, `Single`, `Double`, `Boolean`, `String` (una colección inmutable de caracteres Unicode), `Enum`, `UInt32`, `UInt64` y `Guid`, use el tipo del mismo nombre en el espacio de nombres `System`.

-   Para `UInt8`, use `System.Byte`.

-   Para `Char16`, use `System.Char`.

-   Para la interfaz `IInspectable`, use `System.Object`.

-   Para `HRESULT`, use una estructura con un miembro `System.Int32`.

 Como ocurre con los tipos de interfaz, la única ocasión en que puede ver una evidencia de esta representación es cuando el proyecto de .NET Framework es un componente de [!INCLUDE[wrt](../../../includes/wrt-md.md)] utilizado por una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] creada con JavaScript.

 Otros tipos básicos de [!INCLUDE[wrt](../../../includes/wrt-md.md)] que se usan con frecuencia y que aparecen en el código administrado como sus equivalentes de .NET Framework incluyen la estructura `Windows.Foundation.DateTime`, que aparece en el código administrado como la estructura <xref:System.DateTimeOffset?displayProperty=nameWithType>, y la estructura `Windows.Foundation.TimeSpan`, que aparece como la estructura <xref:System.TimeSpan?displayProperty=nameWithType>.

### <a name="other-differences"></a>Otras diferencias
 En algunos casos, deberá realizar alguna acción para que aparezcan en el código los tipos de .NET Framework en lugar de los tipos de [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Por ejemplo, el <xref:Windows.Foundation.Uri?displayProperty=nameWithType> clase aparece como <xref:System.Uri?displayProperty=nameWithType> en el código de .NET Framework. <xref:System.Uri?displayProperty=nameWithType> permite un URI relativo, pero <xref:Windows.Foundation.Uri?displayProperty=nameWithType> requiere un URI absoluto. Por consiguiente, cuando pase un URI a un método de [!INCLUDE[wrt](../../../includes/wrt-md.md)], debe asegurarse de que sea absoluto. (Consulte [pasar un URI a Windows Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md).)

<a name="WindowsRuntimeComponents"></a>
## <a name="scenarios-for-developing-windows-runtime-components"></a>Escenarios para el desarrollo de componentes de Windows Runtime
 Los escenarios que se admiten para los componentes administrados de [!INCLUDE[wrt](../../../includes/wrt-md.md)] dependen de los principios generales siguientes:

-   Los componentes de [!INCLUDE[wrt](../../../includes/wrt-md.md)] creados con .NET Framework no tienen ninguna diferencia aparente de otras bibliotecas de [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Por ejemplo, si vuelve a implementar un componente nativo de [!INCLUDE[wrt](../../../includes/wrt-md.md)] mediante código administrado, en apariencia no existe ninguna diferencia entre los dos componentes. El hecho de que un componente esté escrito en código administrado es invisible para el código que lo utiliza, incluso si dicho código también es código administrado. Sin embargo, internamente, el componente es código administrado auténtico y se ejecuta en Common Language Runtime (CLR).

-   Los componentes pueden contener tipos que implementan la lógica de la aplicación, controles de la interfaz de usuario de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] o ambos.

    > [!NOTE]
    >  Es recomendable separar los elementos de la interfaz de usuario de la lógica de la aplicación. Además, no se pueden usar controles de la interfaz de usuario de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] en una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] creada para Windows mediante JavaScript y HTML.

-   Un componente puede ser un proyecto de una solución de Visual Studio para una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] o un componente reutilizable que se puede agregar a varias soluciones.

    > [!NOTE]
    >  Si un componente solo se va a usar con C# o Visual Basic, no hay ninguna razón para convertirlo en un componente de [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Si en lugar de ello se crea una biblioteca de clases de .NET Framework ordinaria, no será necesario restringir la superficie de la API pública a los tipos de [!INCLUDE[wrt](../../../includes/wrt-md.md)].

-   Puede liberar las versiones de componentes reutilizables mediante el [!INCLUDE[wrt](../../../includes/wrt-md.md)] <xref:Windows.Foundation.Metadata.VersionAttribute> atributo para identificar qué tipos (y qué miembros dentro de un tipo) se agregaron en versiones diferentes.

-   Los tipos del componente se pueden derivar de los tipos de [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Los controles pueden derivarse de los tipos de controles primitivos del <xref:Windows.UI.Xaml.Controls.Primitives> espacio de nombres o de varios controles, como <xref:Windows.UI.Xaml.Controls.Button>.

    > [!IMPORTANT]
    >  A partir de [!INCLUDE[win8](../../../includes/win8-md.md)] y de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], todos los tipos públicos de un componente administrado de [!INCLUDE[wrt](../../../includes/wrt-md.md)] deben ser sealed. Un tipo de otro componente de [!INCLUDE[wrt](../../../includes/wrt-md.md)] no puede derivarse de ellos. Si se desea proporcionar un comportamiento polimórfico a un componente, puede crear una interfaz e implementarla en los tipos polimórficos.

-   Todos los parámetros y tipos devueltos de los tipos públicos del componente deben ser tipos de [!INCLUDE[wrt](../../../includes/wrt-md.md)] (incluidos los tipos de [!INCLUDE[wrt](../../../includes/wrt-md.md)] definidos por el componente).

 En las secciones siguientes se proporcionan ejemplos de escenarios comunes.

### <a name="application-logic-for-a-includewin8appnamelongincludeswin8-appname-long-mdmd-app-with-javascript"></a>Lógica de aplicación para una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] con JavaScript
 Al desarrollar una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] para Windows mediante JavaScript, puede que algunas partes de la lógica de la aplicación funcionen mejor en código administrado, o que sean más fáciles de desarrollar. JavaScript no puede utilizar las bibliotecas de clases de .NET Framework directamente, pero puede convertir la biblioteca de clases en un archivo .WinMD. En este escenario, el componente de [!INCLUDE[wrt](../../../includes/wrt-md.md)] es una parte integral de la aplicación, por lo que no tiene sentido proporcionar atributos de versión.

### <a name="reusable-includewin8appnamelongincludeswin8-appname-long-mdmd-ui-controls"></a>Controles reutilizables de la interfaz de usuario de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]
 Se puede empaquetar un conjunto de controles relacionados de la interfaz de usuario en un componente reutilizable de [!INCLUDE[wrt](../../../includes/wrt-md.md)]. El componente se puede comercializar por separado o usarse como elemento de las aplicaciones que se creen. En este escenario, tiene sentido utilizar el [!INCLUDE[wrt](../../../includes/wrt-md.md)] <xref:Windows.Foundation.Metadata.VersionAttribute> atributo para mejorar la compatibilidad.

### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>Lógica de aplicación reutilizable de aplicaciones existentes de .NET Framework
 Se puede empaquetar código administrado de aplicaciones de escritorio existentes como un componente independiente de [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Esto permite usar el componente en las aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] creadas con C++ o JavaScript, así como en las aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] creadas con C# o Visual Basic. El control de versiones es una opción si existen varios escenarios de reutilización para el código.

## <a name="related-topics"></a>Temas relacionados

|Título|Descripción|
|-----------|-----------------|
|[Información general de .NET para aplicaciones de la Tienda Windows](https://msdn.microsoft.com/library/windows/apps/br230302(v=VS.110).aspx)|Describe los tipos y miembros de .NET Framework que se pueden usar para crear aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] y componentes de [!INCLUDE[wrt](../../../includes/wrt-md.md)]. (En el Centro de desarrollo de Windows).|
|[Guía básica para aplicaciones de Windows Store usando C# o Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10))|Proporciona recursos clave para ayudarle a empezar a desarrollar aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] mediante C# o Visual Basic, e incluye numerosos tutoriales rápidos, directrices y procedimientos recomendados. (En el Centro de desarrollo de Windows).|
|[Cómo tos (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))|Proporciona recursos clave para ayudarle a empezar a desarrollar aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] mediante C# o Visual Basic, e incluye numerosos tutoriales rápidos, directrices y procedimientos recomendados. (En el Centro de desarrollo de Windows).|
|[Crear componentes de Windows en tiempo de ejecución en C# y Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)|Describe cómo crear un componente de [!INCLUDE[wrt](../../../includes/wrt-md.md)] mediante .NET Framework, explica cómo usarlo como parte de una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] creada para Windows mediante JavaScript y describe cómo depurar la combinación con Visual Studio. (En el Centro de desarrollo de Windows).|
|[Referencia de Windows en tiempo de ejecución](/uwp/api/)|Documentación de referencia para [!INCLUDE[wrt](../../../includes/wrt-md.md)]. (En el Centro de desarrollo de Windows).|
|[Transferencia de un URI a Windows Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md)|Describe un problema que puede surgir cuando se pasa un URI desde el código administrado a [!INCLUDE[wrt](../../../includes/wrt-md.md)] y cómo evitarlo.|
