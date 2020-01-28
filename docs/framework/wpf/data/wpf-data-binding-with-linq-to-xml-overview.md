---
title: Enlace de datos de WPF con LINQ to XML
ms.date: 10/22/2019
ms.topic: conceptual
ms.openlocfilehash: 3c5567c81d2097a1524f5bbbf9010836ca8c0646
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733822"
---
# <a name="overview-of-wpf-data-binding-with-linq-to-xml"></a>Información general sobre el enlace de datos de WPF con LINQ to XML

En este artículo se presentan las características de enlace de datos dinámicos en el espacio de nombres <xref:System.Xml.Linq>. Estas características se pueden usar como origen de datos para los elementos de la interfaz de usuario (IU) en aplicaciones de Windows Presentation Foundation (WPF). Este escenario se basa en las *propiedades dinámicas* especiales de <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> y <xref:System.Xml.Linq.XElement?displayProperty=fullName>.

## <a name="xaml-and-linq-to-xml"></a>XAML y LINQ to XML

El lenguaje XAML es un dialecto XML creado por Microsoft para admitir tecnologías de .NET. Se usa en WPF para representar los elementos de la interfaz de usuario y las características relacionadas como, por ejemplo, el enlace de datos y eventos. En Windows Workflow Foundation, XAML se utiliza para representar la estructura del programa, como por ejemplo el control de programas (*flujos de trabajo*). XAML permite que los aspectos declarativos de una tecnología se separen del código de procedimiento relacionado que define el comportamiento más individualizado de un programa.

XAML puede interactuar con LINQ to XML de dos grandes formas:

- Como los archivos XAML son código XML bien formado, se pueden consultar y manipular mediante tecnologías XML como LINQ to XML.

- Como las consultas de LINQ to XML representan un origen de datos, esas consultas se pueden usar como origen de datos en el enlace de datos para elementos de IU de WPF.

Esta documentación describe el segundo escenario.

## <a name="data-binding-in-the-windows-presentation-foundation"></a>Enlace de datos en el Windows Presentation Foundation

El enlace de datos en WPF permite a un elemento de interfaz de usuario asociar una de sus propiedades con un origen de datos. Un ejemplo sencillo de esto es <xref:System.Windows.Controls.Label>, cuyo texto presenta el valor de una propiedad pública en un objeto definido por el usuario. El enlace de datos de WPF depende de los siguientes componentes:

|Componente|Descripción|
|---------------|-----------------|
|Destino de enlace|El elemento de IU debe estar asociado con el origen de datos. Los elementos visuales de WPF se derivan de la clase <xref:System.Windows.UIElement>.|
|Propiedad de destino|*Propiedad de dependencia* del destino de enlace que refleja el valor del origen de enlace de datos. Las propiedades de dependencia son compatibles directamente con la clase <xref:System.Windows.DependencyObject>, de la que se deriva <xref:System.Windows.UIElement>.|
|Origen de enlace|Objeto de origen para uno o más valores que se proporcionan al elemento de la IU para la presentación. WPF admite automáticamente los siguientes tipos como orígenes de enlace: objetos CLR, objetos de datos ADO.NET, datos XML (de consultas XPath o LINQ to XML) u otro <xref:System.Windows.DependencyObject>.|
|Ruta de acceso de origen|Propiedad del origen de enlace que se resuelve en valor o conjunto de valores que debe enlazar.|

Una propiedad de dependencia es un concepto específico de WPF que representa una propiedad calculada dinámicamente de un elemento de IU. Por ejemplo, las propiedades de dependencia suelen presentar valores predeterminados o valores proporcionados por un elemento primario. Estas propiedades especiales están asistidas por instancias de la clase <xref:System.Windows.DependencyProperty> (y no campos como en las propiedades estándar). Para obtener más información sobre las propiedades de dependencia, vea [Información general sobre las propiedades de dependencia](../advanced/dependency-properties-overview.md).

### <a name="dynamic-data-binding-in-wpf"></a>Enlace de datos dinámicos en WPF

De forma predeterminada el enlace de datos se produce solamente cuando se inicializa el elemento de IU de destino. Se trata de un enlace *único*. Esto es insuficiente para la mayoría de finalidades. Normalmente una solución de enlace de datos requiere que los cambios se propaguen dinámicamente en tiempo de ejecución mediante uno de los siguientes enlaces:

- El enlace *unidireccional* hace que los cambios en un lado se propaguen automáticamente. En la mayoría de casos, los cambios en el origen se reflejan en el destino, aunque la operación inversa puede resultar útil a veces.

- En el enlace *bidireccional*, los cambios en el origen se propagan automáticamente al destino y los cambios en el destino se propagan automáticamente al origen.

Para que se produzca el enlace unidireccional o bidireccional, el origen debe implementar un mecanismo de notificación de cambio, por ejemplo implementando la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> o usando un patrón *PropertyNameChanged* para cada propiedad admitida.

Para más información sobre el enlace de datos, consulte [Enlace de datos (WPF)](/dotnet/framework/wpf/data/data-binding-wpf).

## <a name="dynamic-properties-in-linq-to-xml-classes"></a>Propiedades dinámicas en clases de LINQ to XML

La mayoría de las clases de LINQ to XML no se consideran orígenes de datos dinámicos de WPF adecuados. Parte de la información más útil solo está disponible a través de métodos (y no de propiedades) y las propiedades de esas clases no implementan las notificaciones de cambio. Para admitir el enlace de datos de WPF, LINQ to XML expone un conjunto de *propiedades dinámicas*.

Estas propiedades dinámicas son propiedades en tiempo de ejecución especiales que duplican la funcionalidad de métodos y propiedades existentes en las clases <xref:System.Xml.Linq.XAttribute> y <xref:System.Xml.Linq.XElement>. Se agregaron a esas clases solamente para permitirles actuar como orígenes de datos dinámicos de WPF. Para satisfacer esta necesidad, todas las propiedades dinámicas implementan notificaciones de cambios. En la siguiente sección se describe una referencia detallada de esas propiedades dinámicas, [Propiedades dinámicas de LINQ to XML](linq-to-xml-dynamic-properties.md).

> [!NOTE]
> Muchas de las propiedades públicas estándar, encontradas en las diferentes clases del espacio de nombres <xref:System.Xml.Linq>, se pueden usar para el enlace de datos único. No obstante, recuerde que ni el origen ni el destino se actualizarán dinámicamente con este esquema.

### <a name="access-dynamic-properties"></a>Acceso a propiedades dinámicas

No se puede tener acceso a las propiedades dinámicas de las clases <xref:System.Xml.Linq.XAttribute> y <xref:System.Xml.Linq.XElement> como propiedades estándar. Por ejemplo, en los lenguajes conformes a CLR como C#, no se puede:

- Tener acceso a ellas directamente en tiempo de compilación. Las propiedades dinámicas son invisibles para el compilador y para Visual Studio IntelliSense.

- Detectarlas o tener acceso a ellas en tiempo de ejecución usando la reflexión .NET. Incluso en tiempo de ejecución, no son propiedades en el sentido básico de CLR.

En C#, solamente se puede tener acceso a las propiedades dinámicas en tiempo de ejecución a través de los servicios proporcionados por el espacio de nombres <xref:System.ComponentModel>.

Sin embargo, en un origen XML se puede tener acceso a las propiedades dinámicas a través de una notación sencilla de la siguiente forma:

```xml
<object>.<dynamic-property>
```

Las propiedades dinámicas para esas dos clases se resuelven en un valor que se puede usar directamente o en un indizador que se debe suministrar con un índice para obtener el valor o la colección de valores resultantes. La sintaxis posterior toma la forma:

```xml
<object>.<dynamic-property>[<index-value>]
```

Para obtener más información, consulte [Propiedades dinámicas de LINQ to XML](linq-to-xml-dynamic-properties.md).

Para implementar el enlace dinámico en WPF, se usarán las propiedades dinámicas con soluciones proporcionadas por el espacio de nombres <xref:System.Windows.Data>, especialmente la clase <xref:System.Windows.Data.Binding>.

## <a name="see-also"></a>Vea también

- [Enlace de datos WPF con LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md)
- [Propiedades dinámicas de LINQ to XML](linq-to-xml-dynamic-properties.md)
- [XAML en WPF](../advanced/xaml-in-wpf.md)
- [Enlace de datos (WPF)](/dotnet/framework/wpf/data/data-binding-wpf)
- [Uso del marcado de flujo de trabajo](https://go.microsoft.com/fwlink/?LinkId=98685)
