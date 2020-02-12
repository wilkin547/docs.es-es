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
ms.openlocfilehash: 56c9cb60ab46a583c34f898d20abf85f5ff0fe4c
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123706"
---
# <a name="net-framework-support-for-windows-store-apps-and-windows-runtime"></a>Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows en tiempo de ejecución

El .NET Framework 4,5 admite varios escenarios de desarrollo de software con la Windows Runtime. Estos escenarios se clasifican en tres categorías:

- Desarrollo de aplicaciones de la tienda Windows 8. x con controles XAML, tal como se describe en la [Guía básica para aplicaciones C# de la tienda windows mediante o Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10)), [how (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))y [.net for Windows store apps](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)).

- Desarrollo de bibliotecas de clases para usarlas en las aplicaciones de la tienda Windows 8. x que se crean con el .NET Framework.

- Desarrollar componentes de Windows Runtime, empaquetados en. Archivos WinMD, que se pueden usar en cualquier lenguaje de programación que admita el Windows Runtime. Por ejemplo, consulte [crear componentes de Windows Runtime C# en y Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

En este tema se describe la compatibilidad que proporciona el .NET Framework para las tres categorías y se describen los escenarios para los componentes de Windows Runtime. La primera sección incluye información básica acerca de la relación entre el .NET Framework y el Windows Runtime, y explica algunos singularidades que puede encontrar en el sistema de ayuda y el IDE. En la [segunda sección](#WindowsRuntimeComponents) se describen los escenarios para desarrollar componentes de Windows Runtime.

## <a name="the-basics"></a>Conceptos básicos

El .NET Framework admite los tres escenarios de desarrollo enumerados anteriormente proporcionando .NET para aplicaciones de la tienda Windows 8. x y admitiendo el Windows Runtime mismo.

- Los [espacios de nombres .NET Framework y Windows Runtime](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)#net-framework-and-windows-runtime-namespaces) proporcionan una vista simplificada de las bibliotecas de clases de .NET Framework e incluyen solo los tipos y miembros que se pueden usar para crear aplicaciones de la tienda Windows 8. x y componentes de Windows Runtime.

  - Cuando se usa Visual Studio (Visual Studio 2012 o posterior) para desarrollar una aplicación de la tienda Windows 8. x o un componente de Windows Runtime, un conjunto de ensamblados de referencia garantiza que solo se ven los tipos y miembros pertinentes.

  - Este conjunto de API simplificado se ha simplificado aún más mediante la eliminación de características que se duplican en el .NET Framework o que duplican características Windows Runtime. Por ejemplo, contiene solo las versiones genéricas de los tipos de colección y el modelo de objetos de documento XML se elimina en favor del conjunto de API de Windows Runtime XML.

  - También se quitan las características que simplemente encapsulan la API del sistema operativo, ya que la Windows Runtime es fácil de llamar desde código administrado.

  Para obtener más información acerca de las aplicaciones de la tienda .NET para Windows 8. x, consulte la [información general de .net para aplicaciones de la tienda Windows](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)). Para obtener información sobre el proceso de selección de la API, consulte la entrada [.net para aplicaciones estilo metro](https://devblogs.microsoft.com/dotnet/net-for-metro-style-apps/) en el blog de .net.

- El [Windows Runtime](/uwp/api/) proporciona los elementos de la interfaz de usuario para compilar aplicaciones de la tienda Windows 8. x y proporciona acceso a las características del sistema operativo. Al igual que el .NET Framework, el Windows Runtime tiene metadatos C# que permiten a los compiladores y Visual Basic usar el Windows Runtime la forma en que usan las bibliotecas de clases de .NET Framework. El .NET Framework facilita el uso del Windows Runtime ocultando algunas diferencias:

  - Algunas diferencias en los patrones de programación entre el .NET Framework y el Windows Runtime, como el patrón para agregar y quitar controladores de eventos, están ocultas. Simplemente se usa el patrón de .NET Framework.

  - Algunas diferencias de tipos de uso general (por ejemplo, los tipos primitivos y las colecciones) están ocultas. Simplemente use el tipo de .NET Framework, como se describe en [diferencias que son visibles en el IDE](#DifferencesVisibleInIDE), más adelante en este artículo.

La mayoría de las veces, la compatibilidad de .NET Framework con la Windows Runtime es transparente. En la sección siguiente se describen algunas de las diferencias aparentes entre el código administrado y el Windows Runtime.

<a name="AboutReferenceDocumentation"></a>

### <a name="the-net-framework-and-the-windows-runtime-reference-documentation"></a>La documentación de referencia de .NET Framework y Windows Runtime

Los conjuntos de documentación Windows Runtime y .NET Framework son independientes. Si presiona F1 para mostrar la ayuda sobre un tipo o miembro, se muestra la documentación de referencia del conjunto correspondiente. Sin embargo, si examina la [referencia de Windows Runtime](/uwp/api/) podría encontrar ejemplos que parecen desconcertantes:

- Los temas como la interfaz <xref:Windows.Foundation.Collections.IIterable%601> no tienen sintaxis de declaración para Visual Basic C#o. En su lugar, aparece una nota encima de la sección de sintaxis (en este caso, ".NET: esta interfaz aparece como System. Collections. Generic. IEnumerable\<T >"). Esto se debe a que el .NET Framework y el Windows Runtime ofrecen una funcionalidad similar con distintas interfaces. Además, hay diferencias de comportamiento: `IIterable` tiene un método `First` en lugar de un método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> para devolver el enumerador. En lugar de obligarle a aprender otra manera de realizar una tarea común, el .NET Framework admite el Windows Runtime haciendo que parezca que el código administrado usa el tipo con el que está familiarizado. No verá la interfaz de `IIterable` en el IDE y, por lo tanto, la única manera en que la encontrará en la documentación de referencia de Windows Runtime es examinar la documentación directamente.

- La documentación <xref:Windows.Web.Syndication.SyndicationFeed.%23ctor(System.String,System.String,Windows.Foundation.Uri)> ilustra un problema estrechamente relacionado: sus tipos de parámetros parecen ser diferentes para distintos idiomas. Para C# y Visual Basic, los tipos de parámetros son <xref:System.String?displayProperty=nameWithType> y <xref:System.Uri?displayProperty=nameWithType>. Esto también se debe a que .NET Framework tiene sus propios tipos `String` y `Uri`, y para esos tipos de uso tan general no tiene sentido obligar a los usuarios de .NET Framework a aprender una forma distinta de hacer las cosas. En el IDE, el .NET Framework oculta los tipos de Windows Runtime correspondientes.

- En algunos casos, como la estructura de <xref:Windows.UI.Xaml.GridLength>, el .NET Framework proporciona un tipo con el mismo nombre pero con más funcionalidad. Por ejemplo, existe un conjunto de temas sobre constructores y propiedades relacionados con `GridLength`, pero solo tienen bloques de sintaxis para Visual Basic y C# porque los miembros solo están disponibles en el código administrado. En el Windows Runtime, las estructuras solo tienen campos. La estructura de Windows Runtime requiere una clase auxiliar, <xref:Windows.UI.Xaml.GridLengthHelper>, para proporcionar una funcionalidad equivalente. No verá esa clase del asistente en el IDE cuando escriba código administrado.

- En el IDE, los tipos de Windows Runtime parecen derivar de <xref:System.Object?displayProperty=nameWithType>. Parece que tienen miembros heredados de <xref:System.Object>, como <xref:System.Object.ToString%2A?displayProperty=nameWithType>. Estos miembros funcionan como lo harían si los tipos heredados realmente de <xref:System.Object>y los tipos de Windows Runtime se pueden convertir a <xref:System.Object>. Esta funcionalidad forma parte de la compatibilidad que proporciona el .NET Framework para la Windows Runtime. Sin embargo, si ve los tipos en la documentación de referencia de Windows Runtime, no aparece ningún miembro de este tipo. La documentación para estos miembros aparentemente heredados se proporciona en la documentación de referencia de <xref:System.Object?displayProperty=nameWithType>.

<a name="DifferencesVisibleInIDE"></a>

### <a name="differences-that-are-visible-in-the-ide"></a>Diferencias que son visibles en el IDE

En escenarios de programación más avanzados, como el uso de un componente de C# Windows Runtime escrito en para proporcionar la lógica de la aplicación para una aplicación de la tienda Windows 8. x compilada para Windows con JavaScript, estas diferencias se muestran en el IDE, así como en la documentación de. Cuando el componente devuelva un `IDictionary<int, string>` a JavaScript y lo examine en el depurador de JavaScript, verá los métodos de `IMap<int, string>` porque JavaScript usa el tipo de Windows Runtime. Algunos tipos de colección de uso general que aparecen de manera diferente en los dos lenguajes se muestran en la tabla siguiente:

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

En el Windows Runtime, `IMap<K, V>` y `IMapView<K, V>` se recorren en iteración con `IKeyValuePair`. Cuándo se pasan al código administrado, aparecen como `IDictionary<TKey, TValue>` e `IReadOnlyDictionary<TKey, TValue>`, por lo que naturalmente se usa `System.Collections.Generic.KeyValuePair<TKey, TValue>` para enumerarlas.

La forma en que las interfaces aparecen en código administrado afecta a la forma en que aparecen los tipos que implementan estas interfaces. Por ejemplo, la clase `PropertySet` implementa `IMap<K, V>`, que aparece en código administrado como `IDictionary<TKey, TValue>`. `PropertySet` aparece como si se implementara `IDictionary<TKey, TValue>` en lugar de `IMap<K, V>`, por lo que en código administrado parece tener un método `Add`, que se comporta como el método `Add` en diccionarios de .NET Framework. No parece tener un método `Insert`.

Para obtener más información sobre el uso de la .NET Framework para crear un componente de Windows Runtime y un tutorial que muestra cómo usar este componente con JavaScript, vea [crear componentes de C# Windows Runtime en y Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

### <a name="primitive-types"></a>Tipos primitivos

Para habilitar el uso natural del Windows Runtime en código administrado, aparecen .NET Framework tipos primitivos en lugar de Windows Runtime tipos primitivos en el código. En .NET Framework, los tipos primitivos como la estructura `Int32` tienen muchas propiedades y métodos útiles, como el método `Int32.TryParse`. Por el contrario, los tipos primitivos y las estructuras del Windows Runtime solo tienen campos. Cuando se usan primitivas en el código administrado, aparecen como si fueran tipos de .NET Framework, y se pueden usar las propiedades y métodos de los tipos de .NET Framework como se haría normalmente. La lista siguiente contiene un resumen:

- En el caso de los Windows Runtime primitivas `Int32`, `Int64`, `Single`, `Double`, `Boolean`, `String` (una colección inmutable de caracteres Unicode), `Enum`, `UInt32`, `UInt64`y `Guid`, use el tipo del mismo nombre en el espacio de nombres `System`.

- Para `UInt8`, utilice `System.Byte`.

- Para `Char16`, utilice `System.Char`.

- Para la interfaz `IInspectable`, use `System.Object`.

- Para `HRESULT`, use una estructura con un miembro `System.Int32`.

Al igual que con los tipos de interfaz, la única vez que podría ver evidencia de esta representación es cuando el proyecto de .NET Framework es un componente Windows Runtime que usa una aplicación de la tienda Windows 8. x compilada con JavaScript.

Otros tipos de Windows Runtime básicos, usados comúnmente que aparecen en código administrado como sus .NET Framework equivalentes incluyen la estructura `Windows.Foundation.DateTime`, que aparece en código administrado como la estructura <xref:System.DateTimeOffset?displayProperty=nameWithType>, y la estructura `Windows.Foundation.TimeSpan`, que aparece como la estructura <xref:System.TimeSpan?displayProperty=nameWithType>.

### <a name="other-differences"></a>Otras diferencias

En algunos casos, el hecho de que .NET Framework tipos aparezcan en el código en lugar de Windows Runtime tipos requiere una acción por su parte. Por ejemplo, la clase <xref:Windows.Foundation.Uri?displayProperty=nameWithType> aparece como <xref:System.Uri?displayProperty=nameWithType> en .NET Framework código. <xref:System.Uri?displayProperty=nameWithType> permite un URI relativo, pero <xref:Windows.Foundation.Uri?displayProperty=nameWithType> requiere un URI absoluto. Por consiguiente, al pasar un URI a un método Windows Runtime, debe asegurarse de que es absoluto. Vea [pasar un URI a la Windows Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md).

<a name="WindowsRuntimeComponents"></a>

## <a name="scenarios-for-developing-windows-runtime-components"></a>Escenarios para el desarrollo de componentes de Windows en tiempo de ejecución

Los escenarios que se admiten para los componentes de Windows Runtime administrados dependen de los siguientes principios generales:

- Windows Runtime componentes compilados con el .NET Framework no tienen ninguna diferencia aparente de otras Runtimelibraries de Windows. Por ejemplo, si se vuelve a implementar un componente de Windows Runtime nativo mediante el uso de código administrado, los dos componentes no se distinguen. El hecho de que un componente esté escrito en código administrado es invisible para el código que lo utiliza, incluso si dicho código también es código administrado. Sin embargo, internamente, el componente es código administrado auténtico y se ejecuta en Common Language Runtime (CLR).

- Los componentes pueden contener tipos que implementan la lógica de la aplicación, los controles de la interfaz de usuario del almacén de Windows 8. x o ambos.

  > [!NOTE]
  > Es recomendable separar los elementos de la interfaz de usuario de la lógica de la aplicación. Además, no se pueden usar controles de interfaz de usuario de la tienda Windows 8. x en una aplicación de la tienda Windows 8. x compilada para Windows con JavaScript y HTML.

- Un componente puede ser un proyecto dentro de una solución de Visual Studio para una aplicación de la tienda Windows 8. x o un componente reutilizable que se puede Agregar a varias soluciones.

  > [!NOTE]
  > Si el componente se va a usar solo C# con o Visual Basic, no hay ningún motivo para convertirlo en un componente Windows Runtime. Si se convierte en una biblioteca de clases de .NET Framework normal, no es necesario restringir la superficie de la API pública a los tipos de Windows Runtime.

- Puede publicar versiones de componentes reutilizables mediante el Windows Runtime <xref:Windows.Foundation.Metadata.VersionAttribute> atributo para identificar qué tipos (y qué miembros dentro de un tipo) se agregaron en versiones diferentes.

- Los tipos del componente pueden derivar de tipos de Windows Runtime. Los controles pueden derivarse de los tipos de control primitivos en el espacio de nombres <xref:Windows.UI.Xaml.Controls.Primitives> o de más controles terminados, como <xref:Windows.UI.Xaml.Controls.Button>.

  > [!IMPORTANT]
  > A partir de Windows 8 y el .NET Framework 4,5, todos los tipos públicos de un componente de Windows Runtime administrado deben estar sellados. Un tipo de otro componente de Windows Runtime no puede derivar de ellos. Si se desea proporcionar un comportamiento polimórfico a un componente, puede crear una interfaz e implementarla en los tipos polimórficos.

- Todos los tipos de parámetros y valores devueltos de los tipos públicos del componente deben ser Windows Runtime tipos (incluidos los tipos de Windows Runtime que define el componente).

En las secciones siguientes se proporcionan ejemplos de escenarios comunes.

### <a name="application-logic-for-a-windows-8x-store-app-with-javascript"></a>Lógica de aplicación para una aplicación de la tienda Windows 8. x con JavaScript

Al desarrollar una aplicación de la tienda Windows 8. x para Windows con JavaScript, es posible que algunas partes de la lógica de la aplicación funcionen mejor en código administrado o que sean más fáciles de desarrollar. JavaScript no puede utilizar las bibliotecas de clases de .NET Framework directamente, pero puede convertir la biblioteca de clases en un archivo .WinMD. En este escenario, el componente Windows Runtime es una parte integral de la aplicación, por lo que no tiene sentido proporcionar atributos de versión.

### <a name="reusable-windows-8x-store-ui-controls"></a>Controles de interfaz de usuario de la tienda Windows 8. x reutilizables

Puede empaquetar un conjunto de controles de interfaz de usuario relacionados en un componente de Windows Runtime reutilizable. El componente se puede comercializar por separado o usarse como elemento de las aplicaciones que se creen. En este escenario, tiene sentido usar el atributo Windows Runtime <xref:Windows.Foundation.Metadata.VersionAttribute> para mejorar la compatibilidad.

### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>Lógica de aplicación reutilizable de aplicaciones existentes de .NET Framework

Puede empaquetar el código administrado desde las aplicaciones de escritorio existentes como un componente de Windows Runtime independiente. Esto le permite usar el componente en las aplicaciones de la tienda Windows 8. x C++ compiladas con o JavaScript, así como en las aplicaciones de la tienda C# Windows 8. x compiladas con o Visual Basic. El control de versiones es una opción si existen varios escenarios de reutilización para el código.

## <a name="related-topics"></a>Temas relacionados

|Título|Descripción|
|-----------|-----------------|
|[Información general de .NET para aplicaciones de la Tienda Windows](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140))|Describe los tipos de .NET Framework y miembros que se pueden usar para crear aplicaciones de la tienda Windows 8. x y Windows RuntimeComponents. (En el Centro de desarrollo de Windows).|
|[Guía básica para aplicaciones de la C# tienda Windows mediante o Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10))|Proporciona recursos clave para ayudarle a empezar a desarrollar aplicaciones de la tienda Windows 8. C# x mediante o Visual Basic, incluidos muchos temas de inicio rápido, instrucciones y procedimientos recomendados. (En el Centro de desarrollo de Windows).|
|[Procedimientos (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))|Proporciona recursos clave para ayudarle a empezar a desarrollar aplicaciones de la tienda Windows 8. C# x mediante o Visual Basic, incluidos muchos temas de inicio rápido, instrucciones y procedimientos recomendados. (En el Centro de desarrollo de Windows).|
|[Crear componentes de Windows en tiempo de ejecución en C# y Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)|Describe cómo crear un componente de Windows Runtime mediante el .NET Framework, explica cómo usarlo como parte de una aplicación de la tienda Windows 8. x compilada para Windows mediante JavaScript y describe cómo depurar la combinación con Visual Studio. (En el Centro de desarrollo de Windows).|
|[Referencia de Windows Runtime](/uwp/api/)|Documentación de referencia para el Windows Runtime. (En el Centro de desarrollo de Windows).|
|[Transferencia de un URI a Windows Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md)|Describe un problema que puede surgir al pasar un URI del código administrado al Windows Runtime y cómo evitarlo.|
