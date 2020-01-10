---
title: Propiedades de dependencia
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
ms.openlocfilehash: bd12d05dbba133503778e6df3cd0e6c3e5689d5b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709496"
---
# <a name="dependency-properties"></a>Propiedades de dependencia
Una propiedad de dependencia (DP) es una propiedad normal que almacena su valor en un almacén de propiedades en lugar de almacenarlo en una variable de tipo (campo), por ejemplo.  
  
 Una propiedad de dependencia asociada es un tipo de propiedad de dependencia modelada como métodos estáticos get y set que representan "propiedades" que describen las relaciones entre objetos y sus contenedores (por ejemplo, la posición de un objeto `Button` en un contenedor `Panel`).  
  
 **✓ DO** proporcionan las propiedades de dependencia, si tiene las propiedades para admitir las características de WPF como un estilo, desencadenadores, enlace de datos, animaciones, recursos dinámicos y herencia.  
  
## <a name="dependency-property-design"></a>Diseño de propiedades de dependencia  
 **✓ DO** heredarlo <xref:System.Windows.DependencyObject>, o uno de sus subtipos, al implementar propiedades de dependencia. El tipo proporciona una implementación muy eficaz de un almacén de propiedades y admite automáticamente el enlace de datos de WPF.  
  
 **✓ DO** proporcionar una propiedad CLR normal y el campo estático público de solo lectura almacenar una instancia de <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> para cada propiedad de dependencia.  
  
 **✓ DO** implementar propiedades de dependencia mediante una llamada a métodos de instancia <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> y <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.  
  
 **✓ DO** el nombre del campo estático de propiedad de dependencia aplicando el sufijo del nombre de la propiedad con "Property".  
  
 **X DO NOT** establecer valores predeterminados de las propiedades de dependencia explícitamente en código; establecidos en metadatos.  
  
 Si establece explícitamente un valor predeterminado de la propiedad, puede impedir que esa propiedad se establezca mediante algunos medios implícitos, como un estilo.  
  
 **X DO NOT** colocar código en los descriptores de acceso de propiedad que no sea el código estándar para tener acceso al campo estático.  
  
 Ese código no se ejecutará si la propiedad está establecida por medios implícitos, como un estilo, porque el estilo utiliza el campo estático directamente.  
  
 **X DO NOT** utilizar propiedades de dependencia para almacenar los datos seguros. Incluso se puede tener acceso a las propiedades de dependencia privadas públicamente.  
  
## <a name="attached-dependency-property-design"></a>Diseño de propiedad de dependencia adjunta  
 Las propiedades de dependencia descritas en la sección anterior representan propiedades intrínsecas del tipo declarativo; por ejemplo, la propiedad `Text` es una propiedad de `TextButton`, que la declara. Un tipo especial de propiedad de dependencia es la propiedad de dependencia asociada.  
  
 Un ejemplo clásico de una propiedad adjunta es la propiedad <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>. La propiedad representa la posición de la columna del botón (no de la cuadrícula), pero solo es relevante si el botón está contenido en una cuadrícula, por lo que está "adjunto" a los botones por cuadrículas.  
  
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
  
 **X DO NOT** colocar lógica de validación de propiedad de dependencia en los descriptores de acceso de la propiedad. En su lugar, pase una devolución de llamada de validación al método `DependencyProperty.Register`.  
  
## <a name="dependency-property-change-notifications"></a>Notificaciones de cambio de propiedad de dependencia  
 **X DO NOT** implementar la lógica de la notificación de cambio de descriptores de acceso de propiedad de dependencia. Las propiedades de dependencia tienen una característica de notificaciones de cambio integrada que se debe usar proporcionando una devolución de llamada de notificación de cambio al <xref:System.Windows.PropertyMetadata>.  
  
## <a name="dependency-property-value-coercion"></a>Coerción de valores de propiedad de dependencia  
 La conversión de propiedad tiene lugar cuando el valor dado a un establecedor de propiedad lo modifica el establecedor antes de que se modifique realmente el almacén de propiedades.  
  
 **X DO NOT** implementar la lógica de conversión de los descriptores de acceso de propiedad de dependencia.  
  
 Las propiedades de dependencia tienen una característica de coerción integrada y se pueden usar proporcionando una devolución de llamada de coerción al `PropertyMetadata`.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Patrones de diseño comunes](../../../docs/standard/design-guidelines/common-design-patterns.md)
