---
title: Descripción de Windows Presentation Foundation
description: En este artículo se explica en qué consiste Windows Presentation Foundation (WPF), su relación con .NET Core y las características que proporciona.
ms.date: 07/18/2019
ms.topic: overview
ms.openlocfilehash: 63b2e431b5ab5fd3875887b8b574a77aa12018a6
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "85840331"
---
# <a name="what-is-windows-presentation-foundation"></a>Descripción de Windows Presentation Foundation

Le damos la bienvenida a la Guía de escritorio de Windows Presentation Foundation (WPF), un marco de interfaz de usuario que crea aplicaciones cliente de escritorio para Windows. La plataforma de desarrollo WPF admite un amplio conjunto de características de desarrollo de aplicaciones, incluido un modelo de aplicación, controles, gráficos, y enlace de datos. WPF usa el lenguaje XAML (Lenguaje de marcado de aplicaciones extensible) para proporcionar un modelo declarativo para la programación de aplicaciones.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

Hay dos implementaciones de WPF:

01. La implementación de código abierto hospedada en [GitHub](https://github.com/dotnet/wpf). Esta versión se ejecuta en .NET Core 3.0. El diseñador visual de WPF para XAML requiere, como mínimo, [Visual Studio 2019 versión 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide).

01. La implementación de .NET Framework compatible con Visual Studio 2019 y Visual Studio 2017.

Esta Guía de escritorio está escrita para .NET Core 3.0 y WPF. Para obtener más información sobre la documentación existente para WPF con .NET Framework, vea [Windows Presentation Foundation con .NET Framework](../../framework/wpf/index.md).

## <a name="xaml"></a>XAML

XAML es un lenguaje declarativo basado en XML que WPF usa para tareas como la definición de recursos o elementos de la interfaz de usuario. Los elementos definidos en XAML representan la creación de una instancia de objetos de un ensamblado. XAML no es como la mayoría de los demás lenguajes de marcado, que se interpretan en tiempo de ejecución sin un enlace directo con un sistema de tipos de respaldo.

En el ejemplo siguiente, se muestra cómo se crearía un botón como parte de una interfaz de usuario. Este ejemplo está diseñado para ofrecer una idea de cómo representa XAML un objeto, donde `Button` es el tipo y `Content` es una propiedad.

```xaml
<StackPanel>
    <Button Content="Click Me!" />
</StackPanel>
```

<!--For more information, see [XAML overview (WPF)](../../../framework/wpf/advanced/xaml-overview-wpf.md).-->

### <a name="xaml-extensions"></a>Extensiones XAML

XAML proporciona sintaxis para extensiones de marcado. Las extensiones de marcado se pueden usar para proporcionar valores para propiedades en formularios de atributos, formularios de elementos de propiedad o ambos.

Por ejemplo, el código XAML anterior definía un botón con el contenido visible establecido en la cadena literal `"Click Me!"`, pero el contenido también se puede establecer mediante una extensión de marcado admitida. Una extensión de marcado se define con llaves de apertura y cierre `{ }`. A continuación, el token de cadena inmediatamente posterior a la llave de apertura identifica el tipo de extensión de marcado.

```xaml
<StackPanel>
    <Button Content="{MarkupType}" />
</StackPanel>
```

WPF proporciona diferentes extensiones de marcado para XAML, como `{Binding}` para enlace de datos.

Para más información, vea [Extensiones de marcado y XAML de WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

## <a name="property-system"></a>Sistema de propiedades

WPF proporciona un conjunto de servicios que puede usarse para extender la funcionalidad de la [propiedad](../../standard/base-types/common-type-system.md#properties) de un tipo. Colectivamente, estos servicios se conocen como el *sistema de propiedades de WPF*. Una propiedad respaldada por el sistema de propiedades de WPF se conoce como una propiedad de dependencia.

Las propiedades de dependencia extienden la funcionalidad de una propiedad al proporcionar el tipo <xref:System.Windows.DependencyProperty> que respalda una propiedad. El tipo de propiedad de dependencia es una implementación alternativa del patrón estándar de respaldo de la propiedad con un campo privado.

### <a name="dependency-property"></a>Propiedad de dependencia

En WPF, las propiedades de dependencia se suelen exponer como [propiedades](../../standard/base-types/common-type-system.md#properties) estándar de .NET. En un nivel básico, podría interactuar directamente con estas propiedades y no saber nunca que están implementadas como una propiedad de dependencia.

El propósito de las propiedades de dependencia es proporcionar una manera de calcular el valor de una propiedad en función del valor de otras entradas. Estas otras entradas podrían incluir propiedades del sistema como temas y preferencias del usuario, o bien la propiedad Just-in-Time de las animaciones y el enlace de datos.

Se puede implementar una propiedad de dependencia para proporcionar validación, valores predeterminados y devoluciones de llamada que supervisan los cambios en otras propiedades. Las clases derivadas también pueden cambiar algunas características concretas de una propiedad existente mediante la invalidación de los metadatos de la propiedad de dependencia, en lugar de crear una nueva propiedad o invalidar una existente.

### <a name="dependency-object"></a>Objeto de dependencia

Otro tipo que es clave para el sistema de propiedades de WPF es <xref:System.Windows.DependencyObject>. Este tipo define la clase base que puede registrar y poseer una propiedad de dependencia. Los métodos <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> proporcionan la implementación de respaldo de la propiedad de dependencia para la instancia de objeto de dependencia.

En el ejemplo siguiente se muestra un objeto de dependencia que define un identificador de propiedad de dependencia único denominado `ValueProperty`. La propiedad de dependencia se crea con la propiedad `Value` de .NET.

```csharp
public class TextField: DependencyObject
{
    public static readonly DependencyProperty ValueProperty =
        DependencyProperty.Register("Value", typeof(string), typeof(TextField), new PropertyMetadata(""));

    public string Value
    {
        get { return (string)GetValue(ValueProperty); }
        set { SetValue(ValueProperty, value); }
    }
}
```

La propiedad de dependencia se define como un miembro estático de un tipo de objeto de dependencia, como `TextField` en el ejemplo anterior. La propiedad de dependencia debe registrarse con el objeto de dependencia.

La propiedad `Value` del ejemplo anterior encapsula la propiedad de dependencia y proporciona el patrón estándar de propiedad de .NET al que probablemente está acostumbrado.

<!--For more information, see [Dependency properties overview](../../../framework/wpf/advanced/dependency-properties-overview.md).-->

## <a name="events"></a>Events

WPF proporciona un sistema de eventos superpuesto a los eventos de Common Language Runtime (CLR) de .NET con los que está familiarizado. Estos eventos de WPF se denominan eventos enrutados.

Un evento enrutado es un evento de CLR respaldado por una instancia de la clase `RoutedEvent` y registrado en el sistema de eventos de WPF. La instancia `RoutedEvent` obtenida del registro del evento normalmente se conserva como un miembro del campo `public static readonly` de la clase que registra y, por tanto, *posee* el evento enrutado. La conexión con el evento de CLR del mismo nombre (que a veces se denomina el evento *contenedor*) se logra al invalidar las implementaciones `add` y `remove` del evento de CLR. El mecanismo de conexión y de respaldo del evento enrutado es conceptualmente similar al modo en que una [propiedad de dependencia](#dependency-property) es una propiedad de CLR respaldada por la clase `DependencyProperty` y registrada en el sistema de propiedades de WPF.

La principal ventaja del sistema de eventos enrutados es que los eventos se *traspasan* al árbol de elementos de control en busca de un controlador. Por ejemplo, dado que WPF tiene un modelo de contenido enriquecido, se establece un control de imagen como contenido de un control de botón. Cuando se hace clic con el mouse en el control de imagen, se espera que use los eventos del mouse y así interrumpa las pruebas de posicionamiento que hacen que un botón invoque al evento `Click`. En un modelo de eventos CLR tradicional, esta limitación se solucionaría al adjuntar el mismo controlador a la imagen y al botón. Pero con el sistema de eventos enrutados, los eventos del mouse invocados en el control de imagen (por ejemplo, su selección) se trasladan al control de botón primario.

<!--For more information, including other types of event models, see [Events overview](../../../framework/wpf/advanced/routed-events-overview.md).-->

## <a name="data-binding"></a>Enlace de datos

El enlace de datos de WPF proporciona una manera sencilla y coherente a las aplicaciones para presentar datos e interactuar con ellos. Los elementos se pueden enlazar a datos de distintos tipos de orígenes de datos en forma de objetos de Common Language Runtime (CLR) y XML. WPF también ofrece un mecanismo para transferir datos por medio de operaciones de arrastrar y colocar.

El enlace de datos es el proceso que establece una conexión entre la interfaz de usuario de la aplicación y la lógica de negocios. Si el enlace está configurado correctamente y los datos proporcionan las notificaciones adecuadas, al cambiar el valor de los datos, los elementos enlazados a ellos reflejan los cambios de manera automática. El enlace de datos también puede significar que si cambia una representación externa de los datos de un elemento, los datos subyacentes se actualizan automáticamente para reflejar el cambio. Por ejemplo, si el usuario modifica el valor de un elemento TextBox, el valor de los datos subyacentes se actualiza automáticamente para reflejar ese cambio.

El enlace de datos se puede configurar en XAML por medio de la extensión de marcado `{Binding}`. En el ejemplo siguiente se muestra cómo enlazar a la propiedad `ButtonText` de un objeto de datos. Si se produce un error en ese enlace, se usa el valor de `Click Me!`.

```xaml
<StackPanel>
    <Button Content="{Binding ButtonText, FallbackValue='Click Me!'}" />
</StackPanel>
```

Para obtener más información, vea [Información general sobre el enlace de datos](../data/data-binding-overview.md).

## <a name="ui-components"></a>Componentes de la interfaz de usuario

WPF proporciona muchos de los componentes de interfaz de usuario comunes que se usan en casi todas las aplicaciones Windows, como `Button`, `Label`, `TextBox`, `Menu` y `ListBox`. Históricamente, estos objetos se han denominado controles. Aunque el SDK de WPF sigue usando el término control para referirse a cualquier clase que represente un objeto visible de una aplicación, es importante advertir que una clase no necesita heredar de la clase `Control` para tener una presencia visible. Las clases que heredan de la clase `Control` contienen un objeto `ControlTemplate`, lo que permite al consumidor de un control cambiar radicalmente el aspecto de este sin tener que crear una nueva subclase.

## <a name="styles-and-templates"></a>Estilos y plantillas

Los estilos y plantillas de WPF son un conjunto de características (estilos, plantillas, desencadenadores y guiones gráficos) que permiten a un diseñador de aplicaciones, documentos o interfaces de usuario crear aplicaciones visualmente atractivas y homogeneizar el producto con una apariencia coherente.

Otra característica del modelo de estilos de WPF es la separación de la presentación y la lógica, lo que significa que los diseñadores pueden trabajar en el aspecto de una aplicación con XAML mientras los desarrolladores trabajan en la lógica de programación en otro lugar.

Además, es importante entender los recursos, gracias a los cuales se pueden reutilizar los estilos y las plantillas.

Para más información, vea [Estilos y plantillas](../fundamentals/styles-templates-overview.md).

## <a name="resources"></a>Recursos

Los recursos de WPF son objetos que se pueden volver a usar en diferentes ubicaciones de la aplicación. Los ejemplos de recursos incluyen estilos, plantillas y pinceles de color. Los recursos se pueden definir y mencionar en código y en formato XAML.

Cada elemento de nivel de marco (<xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>) tiene una propiedad `Resources` (que es un tipo <xref:System.Windows.ResourceDictionary>), que contiene recursos definidos. Dado que todos los elementos heredan de un elemento de nivel de marco, todos los elementos pueden definir recursos. Pero es más común definir recursos en un elemento raíz de un documento XAML.

<!--For more information, see [XAML Resources](../../../framework/wpf/advanced/xaml-resources.md).-->

## <a name="next-steps"></a>Pasos siguientes

- [Cree una aplicación WPF.](https://docs.microsoft.com/visualstudio/get-started/csharp/tutorial-wpf?toc=/dotnet/desktop-wpf/toc.json&bc=/dotnet/breadcrumb/toc.json)
- [Examine las diferencias con .NET Framework.](../migration/differences-from-net-framework.md)
- [Obtenga más información sobre XAML.](../fundamentals/xaml.md)
