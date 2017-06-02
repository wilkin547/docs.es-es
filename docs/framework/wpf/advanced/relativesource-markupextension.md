---
title: "Extensi&#243;n de marcado RelativeSource | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RelativeSource"
helpviewer_keywords: 
  - "RelativeSource (extensiones de marcado)"
  - "XAML, RelativeSource (extensión de marcado)"
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Extensi&#243;n de marcado RelativeSource
Especifica las propiedades de un origen de enlace de <xref:System.Windows.Data.RelativeSource>, para su uso en una [Enlazar extensión de marcado](../../../../docs/framework/wpf/advanced/binding-markup-extension.md), o al establecer la propiedad <xref:System.Windows.Data.Binding.RelativeSource%2A> de un elemento <xref:System.Windows.Data.Binding> establecido en XAML.  
  
## Uso de atributos XAML  
  
```  
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>  
```  
  
## Uso de atributos XAML \(anidados en la extensión de enlace\)  
  
```  
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>  
```  
  
## Uso de elementos de objeto XAML  
  
```  
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource Mode="modeEnumValue"/>  
  </Binding.RelativeSource>  
</Binding>  
- or   
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource  
      Mode="FindAncestor"  
      AncestorType="{x:Type typeName}"  
      AncestorLevel="intLevel"  
    />  
  </Binding.RelativeSource>  
</Binding>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`modeEnumValue`|Uno de los siguientes:<br /><br /> -   Token de cadena `Self`; corresponde a un objeto <xref:System.Windows.Data.RelativeSource> creado con su propiedad <xref:System.Windows.Data.RelativeSource.Mode%2A> establecida en <xref:System.Windows.Data.RelativeSourceMode>.<br />-   Token de cadena `TemplatedParent`; corresponde a un objeto <xref:System.Windows.Data.RelativeSource> creado con su propiedad <xref:System.Windows.Data.RelativeSource.Mode%2A> establecida en <xref:System.Windows.Data.RelativeSourceMode>.<br />-   Token de cadena `PreviousData`; corresponde a un objeto <xref:System.Windows.Data.RelativeSource> creado con su propiedad <xref:System.Windows.Data.RelativeSource.Mode%2A> establecida en <xref:System.Windows.Data.RelativeSourceMode>.<br />-   Vea más adelante la información sobre el modo `FindAncestor`.|  
|`FindAncestor`|El token de cadena `FindAncestor`.  Al utilizar este token, se entra en un modo en que `RelativeSource` especifica un tipo de antecesor y, opcionalmente, un nivel del antecesor.  Corresponde a un <xref:System.Windows.Data.RelativeSource> creado con su propiedad <xref:System.Windows.Data.RelativeSource.Mode%2A> establecida en <xref:System.Windows.Data.RelativeSourceMode>.|  
|`typeName`|Necesario para el modo `FindAncestor`.  El nombre de un tipo, que rellena la propiedad <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.|  
|`intLevel`|Opcional para el modo `FindAncestor`.  Un nivel del antecesor \(se evalúa en la dirección del elemento primario en el árbol lógico\).|  
  
## Comentarios  
 Los usos de enlace de `{RelativeSource TemplatedParent}` son una técnica clave que aborda un concepto más amplio de la separación de la interfaz de usuario y la lógica de un control.  Esto permite enlazar desde dentro de la definición de plantilla al elemento primario con plantilla \(instancia de objeto en tiempo de ejecución donde se aplica la plantilla\).  En este caso, [Extensión de marcado TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) es en realidad una forma abreviada de la expresión de enlace siguiente: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.  El uso de `TemplateBinding` o `{RelativeSource TemplatedParent}` solo es relevante dentro del código XAML que define una plantilla.  Para obtener más información, vea [Extensión de marcado TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)  
  
 `{RelativeSource FindAncestor}` se usa principalmente en las plantillas de control o las composiciones autónomas predecibles de la interfaz de usuario, para los casos en que siempre se espera que un control esté en un árbol visual de un tipo de antecesor determinado.  Por ejemplo, los elementos de un control de elementos pueden usar `FindAncestor` para enlazar a propiedades del antecesor del elemento primario del control de elementos.  O bien los elementos que forman parte de la composición de controles en una plantilla pueden usar enlaces `FindAncestor` a los elementos primarios en esa misma estructura de composición.  
  
 En la sintaxis de elementos de objeto para el modo `FindAncestor` que se muestra en las secciones sobre sintaxis XAML, la segunda sintaxis de elementos de objeto se emplea específicamente para el modo `FindAncestor`.  El modo `FindAncestor` necesita un valor de <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.  Debe establecer <xref:System.Windows.Data.RelativeSource.AncestorType%2A> como atributo utilizando una referencia de [x:Type \(Extensión de marcado\)](../../../../docs/framework/xaml-services/x-type-markup-extension.md) al tipo de antecesor que se desea buscar.  Se utiliza el valor de <xref:System.Windows.Data.RelativeSource.AncestorType%2A> al procesar la solicitud de enlace en tiempo de ejecución.  
  
 Para el modo `FindAncestor`, la propiedad <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> opcional puede ayudar a eliminar la ambigüedad en la búsqueda del antecesor en aquellos casos en que sea posible que exista más de un antecesor de ese tipo en el árbol de elementos.  
  
 Para obtener más información sobre cómo usar el modo `FindAncestor`, vea <xref:System.Windows.Data.RelativeSource>.  
  
 `{RelativeSource Self}` es útil para escenarios en los que una propiedad de una instancia debe depender del valor de otra propiedad de la misma instancia y no existe ninguna relación de propiedades de dependencia general \(como la conversión\) entre esas dos propiedades.  Aunque no es habitual que existan dos propiedades en un objeto de modo que los valores sean literalmente idénticos \(y con el mismo tipo\), también puede aplicar un parámetro `Converter` a un enlace que tenga `{RelativeSource Self}` y utilizar el convertidor para realizar la conversión entre los tipos de origen y destino.  Otro escenario de `{RelativeSource Self}` es parte de <xref:System.Windows.MultiDataTrigger>.  
  
 Por ejemplo, el código XAML siguiente define un elemento <xref:System.Windows.Shapes.Rectangle> de forma que, independientemente del valor que se especifique para <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.Shapes.Rectangle> sea siempre un cuadrado: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`  
  
 `{RelativeSource PreviousData}` es útil en las plantillas de datos o en casos donde los enlaces utilizan una colección como origen de datos.  Puede utilizar `{RelativeSource PreviousData}` para resaltar las relaciones entre los elementos de datos adyacentes de la colección.  Una técnica relacionada es establecer un objeto <xref:System.Windows.Data.MultiBinding> entre los elementos actual y anterior del origen de datos, y utilizar un convertidor en dicho enlace para determinar la diferencia entre ambos elementos y sus propiedades.  
  
 En el ejemplo siguiente, el primer <xref:System.Windows.Controls.TextBlock> de la plantilla de elementos muestra el número actual.  El segundo enlace <xref:System.Windows.Controls.TextBlock> es un <xref:System.Windows.Data.MultiBinding> que tiene nominalmente dos componentes <xref:System.Windows.Data.Binding>: el registro actual y un enlace que usa de forma deliberada el registro de datos anterior a través de `{RelativeSource PreviousData}`.  A continuación, un convertidor en el objeto <xref:System.Windows.Data.MultiBinding> calcula la diferencia y la devuelve al enlace.  
  
```  
<ListBox Name="fibolist">  
    <ListBox.ItemTemplate>  
        <DataTemplate>  
            <StackPanel Orientation="Horizontal">  
            <TextBlock Text="{Binding}"/>  
            <TextBlock>, difference = </TextBlock>  
                <TextBlock>  
                    <TextBlock.Text>  
                        <MultiBinding Converter="{StaticResource DiffConverter}">  
                            <Binding/>  
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>  
                        </MultiBinding>  
                    </TextBlock.Text>  
                </TextBlock>  
            </StackPanel>  
            </DataTemplate>  
    </ListBox.ItemTemplate>  
```  
  
 La descripción del concepto de enlace de datos no se incluye aquí, vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 La clase <xref:System.Windows.Data.RelativeSource> define el control para esta extensión de marcado en la implementación del procesador XAML de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 `RelativeSource` es una extensión de marcado.  Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.  Todas las extensiones de marcado de XAML utilizan los caracteres `{` y `}` en su sintaxis de atributo, que es la convención que permite que un procesador de XAML reconozca que el atributo se debe procesar mediante una extensión de marcado.  Para obtener más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## Vea también  
 <xref:System.Windows.Data.Binding>   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Información general sobre declaraciones de enlaces](../../../../docs/framework/wpf/data/binding-declarations-overview.md)   
 [x:Type \(Extensión de marcado\)](../../../../docs/framework/xaml-services/x-type-markup-extension.md)