---
title: Propiedades de dependencia
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75c83dc75d1c86c89169fcc54220ced2a195bfbe
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43866863"
---
# <a name="dependency-properties"></a>Propiedades de dependencia
Una propiedad de dependencia (DP) es una propiedad normal que almacena su valor en un almacén de propiedades en lugar de almacenarlas en una variable de tipo (campo), por ejemplo.  
  
 Una propiedad de dependencia adjunta es un tipo de propiedad de dependencia que se modelan como métodos estáticos de Get y Set, que representa "propiedades" que describen las relaciones entre objetos y sus contenedores (por ejemplo, la posición de un `Button` objeto en un `Panel` contenedor).  
  
 **✓ DO** proporcionan las propiedades de dependencia, si tiene las propiedades para admitir las características de WPF como un estilo, desencadenadores, enlace de datos, animaciones, recursos dinámicos y herencia.  
  
## <a name="dependency-property-design"></a>Diseño de la propiedad de dependencia  
 **✓ DO** heredarlo <xref:System.Windows.DependencyObject>, o uno de sus subtipos, al implementar propiedades de dependencia. El tipo proporciona una implementación muy eficaz de un almacén de propiedades y admite automáticamente el enlace de datos WPF.  
  
 **✓ DO** proporcionar una propiedad CLR normal y el campo estático público de solo lectura almacenar una instancia de <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> para cada propiedad de dependencia.  
  
 **✓ DO** implementar propiedades de dependencia mediante una llamada a métodos de instancia <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> y <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.  
  
 **✓ DO** el nombre del campo estático de propiedad de dependencia aplicando el sufijo del nombre de la propiedad con "Property".  
  
 **X DO NOT** establecer valores predeterminados de las propiedades de dependencia explícitamente en código; establecidos en metadatos.  
  
 Si establece explícitamente un valor predeterminado de la propiedad, puede impedir que esa propiedad se establece por medios implícitas, por ejemplo, una aplicación de estilos.  
  
 **X DO NOT** colocar código en los descriptores de acceso de propiedad que no sea el código estándar para tener acceso al campo estático.  
  
 Que no ejecute código si la propiedad se establece por medios implícitas, como una aplicación de estilos, porque la aplicación de estilos utiliza el campo estático directamente.  
  
 **X DO NOT** utilizar propiedades de dependencia para almacenar los datos seguros. Las propiedades de dependencia incluso privada es accesible públicamente.  
  
## <a name="attached-dependency-property-design"></a>Diseño de la propiedad de dependencia adjunta  
 Las propiedades de dependencia que se describe en la sección anterior representan las propiedades intrínsecas del tipo declarativo. Por ejemplo, el `Text` es una propiedad del `TextButton`, que declara. Un tipo especial de propiedad de dependencia es la propiedad de dependencia adjunta.  
  
 Un ejemplo clásico de una propiedad adjunta es la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> propiedad. La propiedad representa la posición de la columna del botón (no de la cuadrícula), pero solo es pertinente si el botón se encuentra en una cuadrícula, por lo que está "conectado" a los botones mediante cuadrículas.  
  
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
  
 La definición de una propiedad adjunta aspecto en su mayor parte de una propiedad de dependencia normal, excepto en que los descriptores de acceso se representan mediante los métodos Get y Set estáticos:  
  
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
 Las propiedades suelen implementar lo que se denomina validación. Lógica de validación se ejecuta cuando se realiza un intento para cambiar el valor de una propiedad.  
  
 Lamentablemente, los descriptores de acceso de propiedad de dependencia no pueden contener código de validación arbitraria. En su lugar, lógica de validación de propiedad de dependencia debe especificarse durante el registro de la propiedad.  
  
 **X DO NOT** colocar lógica de validación de propiedad de dependencia en los descriptores de acceso de la propiedad. En su lugar, pase una devolución de llamada de validación para `DependencyProperty.Register` método.  
  
## <a name="dependency-property-change-notifications"></a>Notificaciones de cambio de propiedad de dependencia  
 **X DO NOT** implementar la lógica de la notificación de cambio de descriptores de acceso de propiedad de dependencia. Propiedades de dependencia tienen una característica de notificaciones de cambios integrado que se debe usar si se suministra una devolución de llamada de notificación de cambio para el <xref:System.Windows.PropertyMetadata>.  
  
## <a name="dependency-property-value-coercion"></a>Conversión del valor de propiedad de dependencia  
 Conversión de propiedad tiene lugar cuando se modifica el valor dado para un establecedor de propiedades por el establecedor antes de que realmente se modifica el almacén de propiedades.  
  
 **X DO NOT** implementar la lógica de conversión de los descriptores de acceso de propiedad de dependencia.  
  
 Propiedades de dependencia tienen una característica de coerción integrada y se puede usar proporcionando una devolución de llamada coerción la `PropertyMetadata`.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Patrones de diseño comunes](../../../docs/standard/design-guidelines/common-design-patterns.md)
