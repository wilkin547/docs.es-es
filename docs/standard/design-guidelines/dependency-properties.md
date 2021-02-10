---
description: 'Más información acerca de: Propiedades de dependencia'
title: Propiedades de dependencia
ms.date: 10/22/2008
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
ms.openlocfilehash: 78b141d6e8d1bb6bd5cf050a89aa67705111bae3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642310"
---
# <a name="dependency-properties"></a>Propiedades de dependencia

Una propiedad de dependencia es una propiedad normal que almacena su valor en un almacén de propiedades en lugar de en una variable de tipo (campo), por ejemplo.

 Una propiedad de dependencia adjunta es un tipo de propiedad de dependencia modelada como métodos estáticos Get y Set que representan "propiedades" que describen las relaciones entre objetos y sus contenedores (por ejemplo, la posición de un objeto `Button` en un contenedor `Panel`).

 ✔️ Proporcione las propiedades de dependencia, si necesita que las propiedades admitan características de WPF como la aplicación de estilos, los desencadenadores, el enlace de datos, las animaciones, los recursos dinámicos y la herencia.

## <a name="dependency-property-design"></a>Diseño de propiedades de dependencia

 ✔️ Herede de <xref:System.Windows.DependencyObject>, o de uno de sus subtipos, al implementar las propiedades de dependencia. El tipo proporciona una implementación muy eficaz de un almacén de propiedades y admite automáticamente el enlace de datos de WPF.

 ✔️ Proporcione una propiedad de CLR normal y un campo estático público de solo lectura que almacene una instancia de <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> para cada propiedad de dependencia.

 ✔️ Implemente las propiedades de dependencia llamando a los métodos de instancia <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> y <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.

 ✔️ Asigne un nombre al campo estático de la propiedad de dependencia mediante el sufijo del nombre de la propiedad con "Property".

 ❌ NO establezca los valores predeterminados de las propiedades de dependencia explícitamente en el código; hágalo en los metadatos.

 Si establece explícitamente un valor predeterminado de propiedad, puede impedir que esa propiedad se establezca mediante algunos medios implícitos, como una aplicación de estilos.

 ❌ NO coloque código en descriptores de acceso de propiedad que no sean el código estándar para tener acceso al campo estático.

 Ese código no se ejecutará si la propiedad está establecida por medios implícitos, como una aplicación de estilos, porque la aplicación de estilos utiliza el campo estático directamente.

 ❌ NO use propiedades de dependencia para almacenar datos seguros. Incluso a las propiedades privadas de las dependencias se puede acceder públicamente.

## <a name="attached-dependency-property-design"></a>Diseño de las propiedades de dependencia adjuntas

 Las propiedades de dependencia descritas en la sección anterior representan propiedades intrínsecas del tipo declarativo; por ejemplo, la propiedad `Text` es una propiedad de `TextButton`, que la declara. Un tipo especial de propiedad de dependencia es la propiedad de dependencia adjunta.

 Un ejemplo clásico de una propiedad adjunta es la propiedad <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>. La propiedad representa la posición de la columna del botón (no de la cuadrícula), pero solo es relevante si el botón está contenido en una cuadrícula, por lo que está "adjunta" a los botones mediante cuadrículas.

```xaml
<Grid>
    <Grid.ColumnDefinitions>
        <ColumnDefinition />
        <ColumnDefinition />
    </Grid.ColumnDefinitions>

    <Button Grid.Column="0">Click</Button>
    <Button Grid.Column="1">Clack</Button>
</Grid>
```

 La definición de una propiedad adjunta se parece en gran medida a la de una propiedad de dependencia normal, con la excepción de que los descriptores de acceso se representan mediante los métodos estáticos Get y Set:

```csharp
public class Grid {

    public static int GetColumn(DependencyObject obj) {
        return (int)obj.GetValue(ColumnProperty);
    }

    public static void SetColumn(DependencyObject obj, int value) {
        obj.SetValue(ColumnProperty,value);
    }

    public static readonly DependencyProperty ColumnProperty =
        DependencyProperty.RegisterAttached(
            "Column",
            typeof(int),
            typeof(Grid)
    );
}
```

## <a name="dependency-property-validation"></a>Validación de propiedades de dependencia

 A menudo, las propiedades implementan lo que se denomina "validación". La lógica de validación se ejecuta cuando se realiza un intento de cambiar el valor de una propiedad.

 Lamentablemente, los descriptores de acceso de propiedades de dependencia no pueden contener código de validación arbitrario. En su lugar, se debe especificar la lógica de validación de la propiedad de dependencia durante el registro de la propiedad.

 ❌ NO coloque la lógica de validación de propiedades de dependencia en los descriptores de acceso de la propiedad. En su lugar, pase una devolución de llamada de validación al método `DependencyProperty.Register`.

## <a name="dependency-property-change-notifications"></a>Notificaciones de cambios de propiedades de dependencia

 ❌ NO implemente la lógica de notificación de cambios en descriptores de acceso de propiedades de dependencia. Las propiedades de dependencia tienen una característica de notificaciones de cambio integrada que se debe usar proporcionando una devolución de llamada de notificación de cambio a <xref:System.Windows.PropertyMetadata>.

## <a name="dependency-property-value-coercion"></a>Coerción de valores de propiedades de dependencia

 La coerción de propiedades se produce cuando el valor dado a un establecedor de propiedad lo modifica el establecedor antes de que se modifique realmente el almacén de propiedades.

 ❌ NO implemente la lógica de coerción en descriptores de acceso de propiedades de dependencia.

 Las propiedades de dependencia tienen una característica de coerción integrada y se pueden usar proporcionando una devolución de llamada de coerción a `PropertyMetadata`.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](index.md)
- [Patrones de diseño comunes](common-design-patterns.md)
