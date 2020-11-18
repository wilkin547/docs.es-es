---
title: Propiedades de dependencia
ms.date: 10/22/2008
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
ms.openlocfilehash: c6cebd7c6c630af6a1a439b48faccad2aea74a91
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821377"
---
# <a name="dependency-properties"></a>Propiedades de dependencia
Una propiedad de dependencia (DP) es una propiedad normal que almacena su valor en un almacén de propiedades en lugar de almacenarlo en una variable de tipo (campo), por ejemplo.

 Una propiedad de dependencia asociada es un tipo de propiedad de dependencia modelada como métodos estáticos get y set que representan "propiedades" que describen las relaciones entre los objetos y sus contenedores (por ejemplo, la posición de un `Button` objeto en un `Panel` contenedor).

 ✔️ proporcionan las propiedades de dependencia, si necesita que las propiedades admitan características de WPF como el estilo, los desencadenadores, el enlace de datos, las animaciones, los recursos dinámicos y la herencia.

## <a name="dependency-property-design"></a>Diseño de propiedades de dependencia
 ✔️ heredan de <xref:System.Windows.DependencyObject> , o uno de sus subtipos, al implementar las propiedades de dependencia. El tipo proporciona una implementación muy eficaz de un almacén de propiedades y admite automáticamente el enlace de datos de WPF.

 ✔️ proporcionan una propiedad CLR normal y un campo estático público de solo lectura que almacena una instancia de <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> para cada propiedad de dependencia.

 ✔️ implementar las propiedades de dependencia mediante una llamada a métodos <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> de instancia y <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType> .

 ✔️ Asigne un nombre al campo estático de la propiedad de dependencia mediante el sufijo del nombre de la propiedad con "Property".

 ❌ NO establezca los valores predeterminados de las propiedades de dependencia explícitamente en el código; establézcalo en Metadata en su lugar.

 Si establece explícitamente un valor predeterminado de la propiedad, puede impedir que esa propiedad se establezca mediante algunos medios implícitos, como un estilo.

 ❌ No coloque código en los descriptores de acceso de propiedad distintos del código estándar para tener acceso al campo estático.

 Ese código no se ejecutará si la propiedad está establecida por medios implícitos, como un estilo, porque el estilo utiliza el campo estático directamente.

 ❌ No use propiedades de dependencia para almacenar datos seguros. Incluso se puede tener acceso a las propiedades de dependencia privadas públicamente.

## <a name="attached-dependency-property-design"></a>Diseño de propiedad de dependencia adjunta
 Las propiedades de dependencia descritas en la sección anterior representan propiedades intrínsecas del tipo declarativo; por ejemplo, la `Text` propiedad es una propiedad de `TextButton` , que la declara. Un tipo especial de propiedad de dependencia es la propiedad de dependencia asociada.

 Un ejemplo clásico de una propiedad adjunta es la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> propiedad. La propiedad representa la posición de la columna del botón (no de la cuadrícula), pero solo es relevante si el botón está contenido en una cuadrícula, por lo que está "adjunto" a los botones por cuadrículas.

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

 La definición de una propiedad adjunta es principalmente similar a la de una propiedad de dependencia normal, con la excepción de que los descriptores de acceso se representan mediante métodos estáticos get y set:

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
 A menudo, las propiedades implementan lo que se denomina validación. La lógica de validación se ejecuta cuando se realiza un intento de cambiar el valor de una propiedad.

 Desafortunadamente, los descriptores de acceso de propiedad de dependencia no pueden contener código de validación arbitrario. En su lugar, se debe especificar la lógica de validación de la propiedad de dependencia durante el registro de la propiedad.

 ❌ No coloque la lógica de validación de propiedades de dependencia en los descriptores de acceso de la propiedad. En su lugar, pase una devolución de llamada de validación al `DependencyProperty.Register` método.

## <a name="dependency-property-change-notifications"></a>Notificaciones de cambio de propiedad de dependencia
 ❌ No implemente la lógica de notificación de cambios en los descriptores de acceso de propiedad de dependencia. Las propiedades de dependencia tienen una característica de notificaciones de cambio integrada que se debe usar proporcionando una devolución de llamada de notificación de cambios al <xref:System.Windows.PropertyMetadata> .

## <a name="dependency-property-value-coercion"></a>Coerción de valores de propiedad de dependencia
 La conversión de propiedad tiene lugar cuando el valor dado a un establecedor de propiedad lo modifica el establecedor antes de que se modifique realmente el almacén de propiedades.

 ❌ No implemente la lógica de coerción en los descriptores de acceso de propiedad de dependencia.

 Las propiedades de dependencia tienen una característica de coerción integrada y se pueden usar proporcionando una devolución de llamada de coerción a `PropertyMetadata` .

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Directrices de diseño de marco](index.md)
- [Modelos de diseño comunes](common-design-patterns.md)
