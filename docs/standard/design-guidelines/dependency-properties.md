---
title: "Propiedades de dependencia | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Propiedades de dependencia
Una propiedad de dependencia \(DP\) es una propiedad normal que almacena su valor en un almacén de propiedades en lugar de almacenarla en una variable de tipo \(campo\), por ejemplo.  
  
 Una propiedad de dependencia adjunta es un tipo de propiedad de dependencia que se modelan como métodos estáticos de Get y Set, que representa "propiedades" que describen las relaciones entre objetos y sus contenedores \(por ejemplo, la posición de un `Button` de objeto en un `Panel` contenedor\).  
  
 **✓ hacer** proporciona las propiedades de dependencia, si necesita las propiedades para admitir características WPF como estilo, desencadenadores, enlace de datos, animaciones, recursos dinámicos y herencia.  
  
## Diseño de la propiedad de dependencia  
 **✓ hacer** heredan de <xref:System.Windows.DependencyObject>, o uno de sus subtipos, al implementar propiedades de dependencia. El tipo proporciona una implementación muy eficaz de un almacén de propiedades y admite automáticamente el enlace de datos WPF.  
  
 **✓ hacer** proporcionar una propiedad CLR normal y un campo estático público de sólo lectura almacenar una instancia de <xref:System.Windows.DependencyProperty?displayProperty=fullName> para cada propiedad de dependencia.  
  
 **✓ hacer** implementar propiedades de dependencia llamando a métodos de instancia <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=fullName> y <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=fullName>.  
  
 **✓ hacer** el nombre del campo de propiedad de dependencia estática aplicando el sufijo del nombre de la propiedad con "Property".  
  
 **X no** establecer valores predeterminados de las propiedades de dependencia explícitamente en código; establecidos en metadatos.  
  
 Si se establece explícitamente un valor predeterminado de la propiedad, puede impedir que esa propiedad se establece por algunos medios implícitas, como un estilo.  
  
 **X no** colocar código en los descriptores de acceso de propiedad que no sea el código estándar para tener acceso al campo estático.  
  
 Que el código no ejecute si la propiedad se establece por medios implícitas, como un estilo, porque la aplicación de estilos utiliza el campo estático directamente.  
  
 **X no** utilizar propiedades de dependencia para almacenar datos seguros. Propiedades de dependencia incluso privada pueden tener acceso públicamente.  
  
## Diseño de la propiedad de dependencia adjunta  
 Propiedades de dependencia que se describe en la sección anterior representan las propiedades intrínsecas del tipo declarativo. Por ejemplo, el `Text` es una propiedad del `TextButton`, que declara. Un tipo especial de propiedad de dependencia es la propiedad de dependencia adjunta.  
  
 Un ejemplo clásico de una propiedad adjunta es la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=fullName> propiedad. La propiedad representa la posición de la columna \(no de la cuadrícula\) del botón, pero solo es pertinente si el botón está contenido en una cuadrícula, por lo que se "une" a los botones mediante cuadrículas.  
  
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
  
 La definición de una propiedad adjunta aspecto principalmente de una propiedad de dependencia normal, excepto en que los descriptores de acceso se representan mediante los métodos estáticos Get y Set:  
  
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
  
## Validación de propiedades de dependencia  
 Propiedades implementan a menudo lo que se denomina validación. Lógica de validación se ejecuta cuando se realiza un intento para cambiar el valor de una propiedad.  
  
 Desafortunadamente, descriptores de acceso de propiedad de dependencia no pueden contener código de validación arbitraria. En su lugar, lógica de validación de propiedad de dependencia debe especificarse durante el registro de la propiedad.  
  
 **X no** colocar lógica de validación de propiedad de dependencia en los descriptores de acceso de la propiedad. En su lugar, pase una devolución de llamada de validación para `DependencyProperty.Register` \(método\).  
  
## Notificaciones de cambio de propiedad de dependencia  
 **X no** implementar la lógica de notificación de cambio en los descriptores de acceso de propiedad de dependencia. Propiedades de dependencia tienen una característica de notificaciones de cambios integrada que se debe utilizar al proporcionar una devolución de llamada de notificación de cambio para el <xref:System.Windows.PropertyMetadata>.  
  
## Conversión de valores de propiedad de dependencia  
 Conversión de propiedad tiene lugar cuando se modifica el valor dado a un establecedor de propiedad el establecedor antes de modifica realmente el almacén de propiedades.  
  
 **X no** implementar la lógica de conversión en los descriptores de acceso de propiedad de dependencia.  
  
 Propiedades de dependencia tienen una característica integrada la conversión y se puede utilizar proporcionando una devolución de llamada de conversión para el `PropertyMetadata`.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Patrones de diseño comunes](../../../docs/standard/design-guidelines/common-design-patterns.md)