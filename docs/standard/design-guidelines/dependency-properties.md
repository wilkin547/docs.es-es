---
title: Propiedades de dependencia
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 21e2026e7ce0f2dcf1ffc9a328b1bb9630cd8fbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="dependency-properties"></a>Propiedades de dependencia
Una propiedad de dependencia (DP) es una propiedad normal que almacena su valor en un almacén de propiedades en lugar de almacenar en una variable de tipo (campo), por ejemplo.  
  
 Una propiedad de dependencia adjunta es un tipo de propiedad de dependencia que se modelan como métodos estáticos de Get y Set, que representa "propiedades" que describen las relaciones entre objetos y sus contenedores (por ejemplo, la posición de un `Button` objeto en un `Panel` contenedor).  
  
 **✓ HACER** proporcionan las propiedades de dependencia, si tiene las propiedades para admitir las características de WPF como un estilo, desencadenadores, enlace de datos, animaciones, recursos dinámicos y herencia.  
  
## <a name="dependency-property-design"></a>Diseño de la propiedad de dependencia  
 **✓ HACER** heredarlo <xref:System.Windows.DependencyObject>, o uno de sus subtipos, al implementar propiedades de dependencia. El tipo proporciona una implementación muy eficaz de un almacén de propiedades y automáticamente admite enlace de datos WPF.  
  
 **✓ HACER** proporcionar una propiedad CLR normal y el campo estático público de solo lectura almacenar una instancia de <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> para cada propiedad de dependencia.  
  
 **✓ HACER** implementar propiedades de dependencia mediante una llamada a métodos de instancia <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> y <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.  
  
 **✓ HACER** el nombre del campo estático de propiedad de dependencia aplicando el sufijo del nombre de la propiedad con "Property".  
  
 **X DO NOT** establecer valores predeterminados de las propiedades de dependencia explícitamente en código; establecidos en metadatos.  
  
 Si se establece explícitamente un valor predeterminado de la propiedad, puede impedir que algunos medios implícita, por ejemplo, un estilo que se va a establecer esa propiedad.  
  
 **X DO NOT** colocar código en los descriptores de acceso de propiedad que no sea el código estándar para tener acceso al campo estático.  
  
 Que no ejecute código si la propiedad se establece de forma implícita, como un estilo, porque la aplicación de estilos utiliza directamente el campo estático.  
  
 **X DO NOT** utilizar propiedades de dependencia para almacenar los datos seguros. Propiedades de dependencia incluso privada pueden tener acceso públicamente.  
  
## <a name="attached-dependency-property-design"></a>Diseño de la propiedad de dependencia adjunta  
 Propiedades de dependencia que se describe en la sección anterior representan propiedades intrínsecas del tipo declarativo; Por ejemplo, el `Text` es una propiedad del `TextButton`, que lo declara. Un tipo especial de propiedad de dependencia es la propiedad de dependencia adjunta.  
  
 Un ejemplo clásico de una propiedad adjunta es la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> propiedad. La propiedad representa la posición de la columna del botón (no la cuadrícula), pero solo es pertinente si el botón está contenido en una cuadrícula, por lo que se "une" a los botones mediante cuadrículas.  
  
```  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 La definición de una propiedad adjunta es principalmente similar de una propiedad de dependencia normal, excepto en que los descriptores de acceso se representan mediante los métodos Get y Set estáticos:  
  
```  
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
 Propiedades implementan a menudo lo que se denomina validación. Lógica de validación se ejecuta cuando se realiza un intento para cambiar el valor de una propiedad.  
  
 Lamentablemente descriptores de acceso de propiedad de dependencia no pueden contener código de validación arbitraria. En su lugar, lógica de validación de propiedad de dependencia debe especificarse durante el registro de la propiedad.  
  
 **X DO NOT** colocar lógica de validación de propiedad de dependencia en los descriptores de acceso de la propiedad. En su lugar, pase una devolución de llamada de validación para `DependencyProperty.Register` método.  
  
## <a name="dependency-property-change-notifications"></a>Notificaciones de cambio de propiedad de dependencia  
 **X DO NOT** implementar la lógica de la notificación de cambio de descriptores de acceso de propiedad de dependencia. Propiedades de dependencia tienen una característica de notificaciones de cambios integrada que se debe usar si se suministra una devolución de llamada de notificación de cambio para el <xref:System.Windows.PropertyMetadata>.  
  
## <a name="dependency-property-value-coercion"></a>Conversión de valor de propiedad de dependencia  
 Conversión de propiedad tiene lugar cuando se modifica el valor dado un establecedor de propiedad por el establecedor antes de que realmente se modifica el almacén de propiedades.  
  
 **X DO NOT** implementar la lógica de conversión de los descriptores de acceso de propiedad de dependencia.  
  
 Propiedades de dependencia tienen una característica integrada la conversión, y se puede utilizar si se suministra una devolución de llamada de conversión para el `PropertyMetadata`.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Patrones de diseño comunes](../../../docs/standard/design-guidelines/common-design-patterns.md)
